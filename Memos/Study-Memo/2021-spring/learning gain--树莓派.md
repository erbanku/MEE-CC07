#  learning gain--树莓派

## 概念

+ 树莓派就是一个信用卡大小的微型计算机。基于linux系统
+ 当初是为了计算机编程而设计的 

## 应用

+ 首先需要给树莓派通电
+ 然后需要电脑连接到树莓派（SSH+VNCviewer（作用就是图形化））
+ 之后需要写代码完成对树莓派的控制

## 实践

+ 1.闪烁

```\#blingk.py
import RPi.GPIO as GPIO

import time

GPIO.setmode(GPIO.BCM)

GPIO.setup(25,GPIO.OUT)

while True:

GPIO.output(25,GPIO.HIGH)

time.sleep(1)

GPIO.output(25,GPIO.LOW)

time.sleep(1)
```

2.开关控制

```\#button.py
import RPi.GPIO as GPIO

import time

GPIO.setmode(GPIO.BCM)

GPIO.setup(24,GPIO.IN)

GPIO.setup(25,GPIO.OUT)

while True:

inputValue = GPIO.input(24)

if (inputValue == True):

	GPIO.output(25,GPIO.HIGH)

	time.sleep(.01)
else:
	GPIO.output(25,GPIO.LOW)
```

3.模式选择

```#button.py
import RPi.GPIO as GPIO
import time
GPIO.setmode(GPIO.BCM)
GPIO.setup(24,GPIO.IN)
GPIO.setup(25,GPIO.OUT)
a=0
while True:
    inputValue = GPIO.input(24)
    if (inputValue == True):
        a+=1
    if a%3==1:
        GPIO.output(25,GPIO.HIGH)
    elif a%3==2:
        while(1):
            if GPIO.input(24)==True:
                a+=1
                break
            GPIO.output(25,GPIO.HIGH)
            time.sleep(0.5)
            GPIO.output(25,GPIO.LOW)
            time.sleep(0.5)           
    else:
        GPIO.output(25,GPIO.LOW)

```

4.计数器

![image-20210507170026838](C:\Users\86139\AppData\Roaming\Typora\typora-user-images\image-20210507170026838.png)

![image-20210507170047336](C:\Users\86139\AppData\Roaming\Typora\typora-user-images\image-20210507170047336.png)