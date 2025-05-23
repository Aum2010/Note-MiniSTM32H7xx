# OpenMV 

Thank You.
https://www.youtube.com/watch?v=cGHMJrThUq4&ab_channel=%D0%A5%D1%83%D1%82%D0%BE%D1%80%D1%8F%D0%BD%D0%B8%D0%BD%D0%AA%D0%B2IT 
https://gitflic.ru/project/ogneyar/micropython/file?file=STM32%2FSTM32H750&branch=master 

clone 

https://github.com/WeActStudio/MiniSTM32H7xx 

Go to

MiniSTM32H7xx\SDK\openmv\Firmwares\V4.4.1

flash 0x08000000 and 0x90000000 file to board via st-link.
![image-4](/img/image-3.png)

![image-4](/img/image-1.png)

## CameraToDisplayDemo

Type-C board to host

![image-4](/img/image-4.png)

```python
# LCD Example
#
# Note: To run this example you will need a 0.96'' LCD for your Board.
#
# WeAct Studio STM32H7xx
import sensor, image, lcd, time
sensor.reset()                      # Initialize the camera sensor.
sensor.set_pixformat(sensor.RGB565) # or sensor.GRAYSCALE
sensor.set_framesize(sensor.QQVGA)  # Special 160x120 framesize for 0.96'' LCD.
sensor.set_hmirror(True)
sensor.set_vflip(True)
lcd.init(type=2)                    # Initialize the lcd screen.
clock = time.clock()                # Create a clock object to track the FPS.
while(True):
    clock.tick()                    # Update the FPS clock.
    lcd.display(sensor.snapshot())  # Take a picture and display the image.
    print(clock.fps())              # Note: OpenMV Cam runs about half as fast when connected
                                    # to the IDE. The FPS should increase once disconnected.
```


