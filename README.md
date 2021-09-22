# AP-setup

使用CLI命令行方式简单两个步骤为Aerohive AP配置SSID名称

恢复出厂设置后 reset  AP蓝灯闪烁

绿灯常亮 表示有线联网可以上网
白灯常亮  表示登录到云端

打开SecureCRT,波特率：9600 用户名：admin 密码：aerohive  SSH也可用

配置SSID的profile,如SSID名称为AP-CMUI,执行指令: ssid AP-xizhai

将SSID的profile与wifi接口进行关联绑定生效,执行指令:

show interface 
interface wifi0 ssid AP-xizhai    ##2.4G
interface wifi1 ssid AP-xizhai    ##5.8G

给SSID设置密码 

security-object AP-password(随便起名字）

security-object AP-password security protocol-suite wpa2-aes-psk ascii-key 1234567890（你想要的密码）

ssid AP-xizhai security-object AP-password(名字与上面对应）


show ssid AP-xizhai  #查看下配置 是否正确

参考官方给出的CIL 命令格式
https://docs.aerohive.com/330000/docs/help/english/documentation/cli_guide_sr2000_6-5r11.htm
