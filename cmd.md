## Index  

- [print()](#print)  
- [help()](#help)  
- [pyb.info()](#info)  
- [pyb.millis()](#millis)  
- [pyb.Pin(pin)](#pin)  


## print

```
>>> print("hello, pyboard!")
hello, pyboard!
```

串口发送命令加 **回车换行** 才执行. 


## help  

```
>>> help()
Welcome to MicroPython!

For online help please visit http://micropython.org/help/.

Quick overview of commands for the board:
  pyb.info()    -- print some general information
  pyb.delay(n)  -- wait for n milliseconds
  pyb.millis()  -- get number of milliseconds since hard reset
  pyb.Switch()  -- create a switch object
                   Switch methods: (), callback(f)
  pyb.LED(n)    -- create an LED object for LED n (n=1,2,3,4)
                   LED methods: on(), off(), toggle(), intensity(<n>)
  pyb.Pin(pin)  -- get a pin, eg pyb.Pin('X1')
  pyb.Pin(pin, m, [p]) -- get a pin and configure it for IO mode m, pull mode p
                   Pin methods: init(..), value([v]), high(), low()
  pyb.ExtInt(pin, m, p, callback) -- create an external interrupt object
  pyb.ADC(pin)  -- make an analog object from a pin
                   ADC methods: read(), read_timed(buf, freq)
  pyb.DAC(port) -- make a DAC object
                   DAC methods: triangle(freq), write(n), write_timed(buf, freq)
  pyb.RTC()     -- make an RTC object; methods: datetime([val])
  pyb.rng()     -- get a 30-bit hardware random number
  pyb.Servo(n)  -- create Servo object for servo n (n=1,2,3,4)
                   Servo methods: calibration(..), angle([x, [t]]), speed([x, [t]])
  pyb.Accel()   -- create an Accelerometer object
                   Accelerometer methods: x(), y(), z(), tilt(), filtered_xyz()

Pins are numbered X1-X12, X17-X22, Y1-Y12, or by their MCU name
Pin IO modes are: pyb.Pin.IN, pyb.Pin.OUT_PP, pyb.Pin.OUT_OD
Pin pull modes are: pyb.Pin.PULL_NONE, pyb.Pin.PULL_UP, pyb.Pin.PULL_DOWN
Additional serial bus objects: pyb.I2C(n), pyb.SPI(n), pyb.UART(n)

Control commands:
  CTRL-A        -- on a blank line, enter raw REPL mode
  CTRL-B        -- on a blank line, enter normal REPL mode
  CTRL-C        -- interrupt a running program
  CTRL-D        -- on a blank line, do a soft reset of the board
  CTRL-E        -- on a blank line, enter paste mode

For further help on a specific object, type help(obj)
For a list of available modules, type help('modules')
```  


## info

```
>>> pyb.info()
ID=25001e00:08473634:38383731
S=168000000
H=168000000
P1=42000000
P2=84000000
_etext=806ba54
_sidata=806ba54
_sdata=20000000
_edata=20000024
_sbss=20000024
_ebss=20002690
_estack=20020000
_ram_start=20000000
_heap_start=20002690
_heap_end=2001c000
_ram_end=20020000
qstr:
  n_pool=0
  n_qstr=0
  n_str_data_bytes=0
  n_total_bytes=0
GC:
  102400 total
  720 : 101680
  1=22 2=7 m=3
LFS free: 90624 bytes
```  


## millis

```
>>> pyb.millis()
380718
```  

Ctrl+V粘贴命令不管用... 按下Ctrl+D软件复位, 但是millis()并不会清零. 也就是说 软件复位不会改变millis()的值.   



## pin

```
>>> pyb.Pin('X1')
Pin(Pin.cpu.A0, mode=Pin.IN)
```  


