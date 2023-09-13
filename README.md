<img src="https://www.tijuana.tecnm.mx/wp-content/uploads/2021/05/SCG-LOGOTIPO-2021-scaled.jpg">

# Datos
- Instituto Tecnológico de Tijuana
- Sistemas programables
- Prof. René Solis Reyes
- Leonardo Rangel Vizcarra - 20211830

<div align = "center">
  
#  MPU6050 Accelerometer + Gyroscope

</div>

## Imagenes
<img style="max-width:30%" src = "https://m.media-amazon.com/images/I/51eWrHRzWJL._AC_UF894,1000_QL80_.jpg">
<img style="max-width:30%" src = "https://j5d2v7d7.stackpathcdn.com/wp-content/uploads/2019/04/MPU-6050-pinout.gif">

## Especificaciones
- Salida digital de 6 ejes.
- Giroscopio con sensibilidad de ±250, ±500, ±1000, y ±2000dps
- Acelerómetro con sensibilidad de ±2g, ±4g, ±8g y ±16g
- Algoritmos embebidos para calibración
- Sensor de temperatura digital
- Entrada digital de video FSYNC
- Interrupciones programables
- Voltaje de alimentación: 2.37 a 3.46V
- Voltaje lógico: 1.8V±5% o VDD
- 10000g tolerancia de aceleración máxima
## Código de ejemplo
```python
#Shows Pi is on by turning on LED when plugged in
LED = machine.Pin("LED", machine.Pin.OUT)
LED.on()

from imu import MPU6050
from time import sleep
from machine import Pin, I2C

i2c = I2C(0, sda=Pin(0), scl=Pin(1), freq=400000)
imu = MPU6050(i2c)

while True:
    ax=round(imu.accel.x,2)
    ay=round(imu.accel.y,2)
    az=round(imu.accel.z,2)
    gx=round(imu.gyro.x)
    gy=round(imu.gyro.y)
    gz=round(imu.gyro.z)
    tem=round(imu.temperature,2)
    print("ax",ax,"\t","ay",ay,"\t","az",az,"\t","gx",gx,"\t","gy",gy,"\t","gz",gz,"\t","Temperature",tem,"        ",end="\r")
    sleep(0.2) 
```
