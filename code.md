
## blink
```Python
import pyb

led = pyb.LED(2)    #Red
while True:
    led.toggle()
    pyb.delay(1000)
```


```Python
led = pyb.LED(2)
intensity = 0
while True:
    intensity = (intensity + 1) % 255
    led.intensity(intensity)
    pyb.delay(20)
```