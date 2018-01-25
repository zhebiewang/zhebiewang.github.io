# Install Issue

1. 风扇引线接错，风扇装反了
2. Noobs 下载太慢，用国外电脑下载，在用ftp传到本地
3. 出现please wait while noobs initialises 对话框，一直不消失。 拔掉网线，重新启动下。在离线状态下安装
4. 配置国内源，只修改了/etc/apt/source.list 没有修改 etc/apt/source.list.d/raspi.list。详见<https://www.janecc.com/pi-raspberry-3-using-ali-cloud-mirror-cloud.html>
5. 配置无线AP， 在/etc/default/hostapd 修改config 文件的设置出错， 把应该设置给变量DAEMON_CONF 错给了变量 DAEMON_OPTS。 详见<https://frillip.com/using-your-raspberry-pi-3-as-a-wifi-access-point-with-hostapd/>

