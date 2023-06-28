V1.1版本修改
1.调整[safe_z_home]速度为200
2.调整[printer]，max_accel限制为5000，开启max_z_velocity:5,max_z_accel: 100
3.调整[extruder]，pressure_advance禁用
4.调整[extruder]，ender3S1 PRO的喷嘴max_temp是305，ender3S1/ender3V2max_temp是265
5.调整[bed_mesh]，ender3V2的speed限制为120，ender3S1 PRO/ender3S1speed限制为150
6.增加延时摄影配置[include /mnt/UDISK/printer_config/timelapse.cfg]

V1.2版本修改
1.去除冗余配置代码
2.修改[virtual_sdcard]值为path: ~/gcode_files
3.修改Ender 3V2 [extruder] [heater_bed]值min_temp为0
4.新增klipper下位机固件编译和安装说明

V1.3版本修改
1.紧急修复[display]字段导致CR6SE喷嘴发热问题。此字段适用于点阵屏，音速屏无用，删除该字段
2.修复Ender3 V2-CRtouch [stepper_z]，enable_pin: !PC3，未启用导致Z轴不抬升的问题
3.修改机型名称Ender 3V2-CRtouch为Ender 3V2 ABL

V1.4版本修改
1.修改Ender3-S1 [safe_z_home] home_xy_position:155,155
2.修改[stepper_x] homing_speed: 80
3.修改[stepper_y] homing_speed: 80
4.修改Ender-3S1/S1 Pro [stepper_y] position_max: 230
5.新增机型成型尺寸注释 # printer_size: 220x220x270
6.新增[adxl345] spi_speed: 2000000

V1.5版本修改
1.修复自动调平时，报错超范围

V1.6版本修改
1.去掉Ender3-V2系列断料检测配置
2.新增Ender3-V2-V4.2.7主板配置文件
3.新增Ender3V2-CRtouch-V4.2.7主板配置文件
4.配置文件名修改统一风格

V1.7版本修改
1.适配自适应调平，增加双插值算法
2.机型命名修改规范

V1.8版本修改
1.增加[verify_heater extruder] 
      check_gain_time: 200 
      hysteresis: 5
2.修改默认[extruder]和[heater_bed]PID值

V1.9版本修改
1.修改Ender3-S1/S1Pro中[safe_z_home] home_xy_position: 145,155
2.修改Ender3-S1/S1Pro中[bltouch] x_offset: -30.0

V2.0版本修改
1.修改Ender3-S1/S1 Pro中 [printer] max_z_velocity: 10   max_z_accel: 1000
2.增加Ender3-S1/S1 Pro/V2 [printer] square_corner_velocity: 5.0

V2.1版本修改
1.修改Ender3-S1/S1 Pro 中[stepper_z] position_max: 275
2.修改Ender3-V2 中[stepper_z] position_max: 255

V2.2版本修改
1.修改[gcode_macro CANCEL_PRINT]宏定义
2.修改Ender3-V2-CRtouch 中[stepper_x] position_max: 240
3.更新固件添加异常加热底层逻辑

V2.3版本修改
1.修改Ender3-S1/S1 Pro [stepper_x] position_min: -6 position_endstop: -6 
2.删除Ender3-V2 宏命令[delayed_gcode AUTOSTART]

V2.4版本修改
1.修改Ender3-S1/S1 Pro [stepper_x] position_min: -3 position_endstop: -3 

V2.5版本修改
1.修改Ender3-S1/S1 Pro [stepper_x] position_min: -5 position_endstop: -5 
2.修改Ender3-S1/S1 Pro 打印成型范围

V2.6版本修改
1.新增机型Ender3-V2 Neo
2.新增机型Ender3-s1pro-103
2.新增宏定义[gcode_macro G29]

V2.7版本修改
1.修改Ender3-V2-CRtouch-V4.2.7 [stepper_z] 修改touch配置

V2.8版本修改
1.新增七款机型配置文件和固件
2.补偿震动补偿默认值
3.修改touch版本配置文件中 [bltouch] speed值

V2.9版本修改
1.Cr10Smart,调整[probe] speed: 3

V3.0版本修改
1.Cr10Smart,调整归零宏指令，避免撞模型

V3.1版本修改
1.新增七款机型配置文件和固件
2.规范显示名称

V3.2版本修改
1.修改Ender3 Pro中 [bltouch] sensor_pin: ^PB1
2.新增11款机型 

V3.3版本修改
1.新增4款机型
2.去除部分配置文件内冗余注释

V3.4版本修改
1.新增CR6SE v4.3.2主板配置
2.修改Ender3 S1/S1Pro中显示成型范围改为220*220*270
3.增加[gcode_arcs]
4.统一喷嘴最高温度全金属的喉管最高温度设定为315℃，非全金属的设定为265℃

V3.5版本修改
1.新增Q5,SR,Ender5S1-new,CR-10 M4机型适配
2.新增串口固件支持

V3.6版本修改
1.CR-10 M4问题修改
2.新增Prusa MK3S,Ender-3 Neo,CR-10 V2机型支持
3.新增[exclude_object]