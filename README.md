## 官方提供的资料位于doc文件夹内，由于部分源码已经过修改，所以以此文档为准。


C板的陀螺仪的坐标设定：

站在车体后方,以C板平放，R标面向自己，以左下角为观测点，逆时针为正方向，对应板子的三轴
!!!注意,C板固定应该平放!!!!




## 操作手参数：

遥控器控制:

左侧按键：上 打开和关闭摩擦轮
         中 无状态
         下 从中拨到下,快速拨回中为单发
            从中拨到下,停留为连发
​		  


右侧按键：上为跟随底盘

​		  中为跟随云台

​		  下为刹车，云台静止

拨杆：

左侧拨杆控制底盘前后左右，右侧拨杆控制云台pitch和yaw，在跟随底盘模式下也控制底盘旋转。





键盘控制：将遥控器左右按键拨至中间 !!! 

底盘：
    W A S D 前后左右平移
    F 小陀螺 
    CTRL 扭腰
    SHIFT 长按 超级电容加速

云台:
    Q 左90度转头 E 右 90度转头 V 180度转头
    CTRL+Q 左45度角对敌  
    CTRL+E 右45度角对敌
射击: 
    G 打开摩擦轮  
    R 双击 打开弹仓
    鼠标左键 单击单发 长按连发 
    鼠标右键 单击打开自瞄 再次单击关闭自瞄




​	



## 硬件连接说明：
从左向右数:
裁判串口线: C板UART1  G TX RX
裁判学生串口接口 RX TX G
视觉串口线: C板UART2  RX TXV G V

CAN1: L H
CAN2: V G H L

底盘电机：can2  ID 为1 2 3 4 右前，左前，左后，右后

云台电机：can1 yaw 9 pitch 10 

摩擦轮电机：can1 left 5 right 6

拨盘电机：can1 7

弹仓舵机: 左边数第2个PWM
限位舵机: 左边数第3个PWM  


射弹 触发条件为  BUTTEN_TRIG_PIN 为低电平 对应C板最左侧的PWM口
        


关于电机正反装
#define YAW_TURN    0
#define PITCH_TURN  0

这两个宏定义与电机正反装相关,当yaw轴电机转子与云台相对运动时,YAW_TURN为0,否则为1;pitch轴电机转子与云台相对运动时,PITCH_TURN为0,否则为1,


## 校准操作说明：




开启校准模式：          左摇杆右下，右摇杆左下  且左右按键拨至下档

陀螺仪校准           左摇杆左下，右摇杆右下  且左右按键拨至下档

云台校准               左摇杆左上，右摇杆右上  且左右按键拨至下档

底盘校准             左摇杆右上，右摇杆左上   且左右按键拨至下档


