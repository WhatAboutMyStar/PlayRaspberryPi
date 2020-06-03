# 树莓派连接WiFi
使用putty软件ssh远程登录到了树莓派中之后，一个基本的需求就是能够上网。 <br>

## 连接WiFi的方法
- 把树莓派的tf卡取下来，插到读卡器上，然后插入电脑
- 在读卡器的根目录下面建立一个文件，文件名为wpa_supplicant.conf
- 在文件里面写入 <br>
```
country=CN
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
network={
  ssid="你的WiFi名字"
  psk="密码"  
  key_mgmt=WPA-PSK 
  priority=1 
}
```
其中
- ssid 里面应该填入WiFi的名字
- psk 应该写入WiFi的密码
- key_mgmt=WPA-PSK 是WiFi的加密方式
- priority 是优先级
---------------------------------
- 保存后将卡重新插入到树莓派中，开机时树莓派就会自动连接WiFi
