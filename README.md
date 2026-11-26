1.test4为任务一 定时器中断消抖按键+led模式切换

2.test5为任务二 pwm呼吸灯与舵机驱动
（1）呼吸灯采用的是tim1 psc为15 arr为999 采用正弦式变化 时间的获取用了gettick（ms）
ccr=duty*(999+1)
占空比公式 duty=0.5*sin(3.14*t)+0.5; t为（s）

（2）舵机驱动采用的是tim2 psc为15 arr为9999 采用余弦式变化 时间的获取用了gettick
角度duty2=1.57*t
ccr2=（1500-1000*cos(duty2)）
占空比公式 =（1500-1000*cos(duty2)）/10000;（duty2为角度）

3.test6为任务三 num为adc volt为电压值
