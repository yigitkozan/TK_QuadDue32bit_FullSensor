TK_QuadDue32bit_FullSensor
==========================
TK Quad 3D Shop
http://quad3d-tin.lnwshop.com/

Video

http://www.youtube.com/watch?v=JGk_WfaXbeo&feature=youtu.be

Picture

![](https://cloud.githubusercontent.com/assets/9403558/4783264/23fb4728-5d1f-11e4-9f8e-9581094c09ac.jpg)

below

![](https://cloud.githubusercontent.com/assets/9403558/4783269/42e3c1f6-5d1f-11e4-9a03-1425c7fc3152.jpg)

front

![](https://cloud.githubusercontent.com/assets/9403558/4783271/628e6b50-5d1f-11e4-9da8-9cecc5da89d7.jpg)

<picture> https://drive.google.com/file/d/0B4UGzNJoSnKmekQ0cjIwZHdDT00/view?usp=sharing <picture>

support:  Arduino Due

• Atmel SAM3X8E ARM Cortex-M3 CPU 32-bit a 84 MHz clock, ARM core microcontroller

• CJMCU-117 MPU-9250+MS5611 high precision 9 axis 10DOF //SPI 1 MHz 

• MPU6050 Gyro Accelerometer //I2C 400kHz nois gyro +-0.05 deg/s , acc +-0.04 m/s^2

• MS561101BA Barometer//I2C 400kHz

• HMC5883L Magnetometer //I2C 400kHz

• ADNS3080 Optical Flow Sensor//SPI 1 MHz 

• Ultrasonic_HC-SR04

• Distance Measuring Sensor 20-150cm (SHARP GP2Y0A02YK0F)

• GPS NEO-7N //Rx 1 Tx 1 

• GPS NEO-6 //

• CMUCam5 Pixy //Rx 2 Tx 2

• SMD RGB three colors LEDs module //RGB = pin 5,4,3

• Laser Head Transmitter Sensor Module //pin 40

----------rx-----------  
A8 = CPPM

/*
//Test By tinnakon kheowree

//tinnakon_za@hotmail.com

//tinnakonza@gmail.com

//https://www.facebook.com/tinnakonza

//10/10/2556    write Test_AllSensorV1

//19/10/2556    write TK_Quad32bit_FullSensor_V1

//19/10/2556    write TK_Quad32bit_FullSensor_V2  , PIDA ,  Altitude , Optical Flow Sensor ,CMUCam5 Pixy

//20/10/2556    write TK_Quad32bit_FullSensor_V3  ,Laser Head Transmitter , "BaroSPI_MS5611.h"


การเขียนโปรแกรม Quadrotor พื้นฐาน เรียบเรียงโดย ทินกร เขียวรี
หัวข้อที่ต้องรู้ในการเขียนโปรแกรม บอร์ด MEGAWAP_V2_AIO

1.1. ความเร็วลูป 100 Hz, 50 Hz, 20 Hz, 10 Hz, 5 Hz, 1 Hz  
100 Hz ทำ อ่านเซนเซอร์ gyro,acc, ควบคุม PID , Filter
50 Hz ทำ อ่านค่ารีโมท
20 Hz อ่านค่าจาก ett1280
10 Hz ทำ Automatic  Takeoff , waypoint navigation  และ Landing อ่านค่า   
Magnetometer และ Chack_Command จาก Radio Telemetry Kit 433Mhz , CRIUS Bluetooth Module, Command By Remote  idle-up settings 0,1,2
5 Hz คำนวณ GPS ควบคุมต่ำแหน่ง
1 Hz แสดงสถานะหลอดไฟ LED ทำ Accelerometers trim โดยใช้ รีโมท 

1.2. การอ่านค่าเซนเซอร์ gyroscope , accelerometer, magnetometer

1.3. การอ่านค่ารีโมท PWM 1-2 ms

1.4. การกำหนดค่าเริ่มต้นใน setup()

1.5. การทำ sensor Calibration และการแปลงหน่วย rad/s , deg/s , m/s^2

1.6. การลดสัญญานรบกวน sensor , Moving average  filter , Low pass  filter

1.7. วิธีการหาค่ามุม , quaternion , direction cosine matrix , Euler angles,  Rotation matrix
Body Fixed Frame, Earth-Fixed frame

1.8. การอ่านค่า GPS latitude and longitude , ความเร็วการเคลื่อนที่ Earth-Fixed frame

1.9. การควบคุม PID–I , Roll, Pitch, Yaw

1.10. การควบคุมความสูงใช้ State feedback control

1.11. เงื่อนไข Automatic  Takeoff , waypoint navigation  และ Landing

1.12. การควบคุมต่ำแหน่ง GPS ใช้ PD control

1.13. การทำ Motor mixing theory,  Quad +

1.14. การสั่ง PWM 1-1.9 ms ให้มอเตอร์หมุน

1.15. การทำ Electronic Speed Controllers Calibration 1 - 1.9 ms

1.16. การทำ Accelerometers trim โดยใช้ รีโมท

1.17. การทำ Calibration sensor Magnetometer หาค่า Max , Min

1.18. การทำ ARM and DISARM ไม่ให้มอเตอร์หมุนและหมุน

บอร์ด ET-EASY MEGA1280 (DUINO MEGA)

2.1. ความเร็วลูป 20 Hz, 10 Hz, 5 Hz
20 Hz อ่านค่า Ultrasonic ,ทำ Filter , ตรวจสอบการเชื่อมต่อ GPS 2 ตัว ,ส่งค่าความสูงและGPS ไปบอร์ด MEGAWAP_V2_AIO
      10 Hz ปริ้นค่าดู  5 Hz อ่านค่า GPS 

2.2. การอ่านค่าเซนเซอร์ Ultrasonic_HC-SR04, Trigger, Echo

2.3. การอ่านค่าเซนเซอร์ GPS ใช้ NMEA_BINARYxx settings ของ MultiWii

2.4. การกำหนดค่าเริ่มต้นใน setup()

2.5. การลดสัญญานรบกวน sensor , Low pass  filter

2.6. การส่งข้อมูล RS232 data 22 byte

โหลด Code ที่
https://github.com/QuadTinnakon?tab=repositories

เอกสาร
https://drive.google.com/file/d/0B4UGzNJoSnKmVlNFeFpnNTFiZzA/view?usp=sharing

เนื้อหาที่เกี่ยงข้องกับการพัฒนา
Optical flow-based 
http://www.dae.mi.th/aeroblog/?p=2796

Kalman Filter
http://library.rtna.ac.th/web/RTNA_Journal/y.4c.4/05.pdf

http://diydrones.com/profiles/blogs/arduino-due-32bit-quadrotor-testing-altitude-hold

http://www.youtube.com/watch?v=JGk_WfaXbeo&feature=youtu.be

https://www.facebook.com/tinnakonza

http://www.youtube.com/user/tinnakon6094

http://www.eng.rmutsb.ac.th/

https://drive.google.com/#my-drive
