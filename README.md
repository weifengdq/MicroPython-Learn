# MicroPython-Learn  

## index
- [run](#run)  
- [led](#led)  
- [blink](#blink)  

## run
在main.py中编写代码, **保存**, 串口调试中按下 Ctrl+D 软件复位, 就可以运行程序了. 或者按下板子上的 **RST** 按键. 或者拔掉USB再插上.  

## led
help()中关于LED的介绍如下:  

>  pyb.LED(n)    -- create an LED object for LED n (n=1,2,3,4)
                   LED methods: on(), off(), toggle(), intensity(<n>)

1, 2, 3, 4与颜色的对应关系如下:  


n | LED 
---------|----------
 1 | Green 
 2 | Red 
 3 | Yellow 
 4 | Blue

main.py输入:  

```Python
import pyb
pyb.LED(4).on()
```

保存, 串口调试中 Ctrl+D, 可以看到蓝色的LED亮起来了.  



## blink

```Python
import pyb

leds = [pyb.LED(i) for i in range(1,5)]
for led in leds:
    led.off()

n = 0
try:
   while True:
      n = (n + 1) % 4
      leds[n].toggle()
      pyb.delay(50)
finally:
    for led in leds:
        led.off()
```

