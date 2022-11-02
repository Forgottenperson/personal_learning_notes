## 個人使用桌面環境安裝
* pacman -Syu alsa-firmware alsaplayer alsa-lib alsa-utils alsa-plugins //Pi驅動程式
* i3(i3-wm) // desktop
* ranger //filemanager
* urxvt(rxvt-Unicode) //terminal 需要設定 config
* omxplayer
* streamlink
* NetworkManager
* ssh

/boot/config.txt
----

```
 http://elinux.org/RPi_config.txt
 sudo amixer cset numid=3 <n>
 0=auto, 1=analog, 2=hdmi
```
=============================
```
hdmi_force_hotplug=1
hdmi_force_edid_audio=1
arm_control=0x200 64bit
```

 ---------------------------------------------------------------

python install --upgrade youtube-dl
```
youtube-dl -F <youtube-url> 
omxplayer `youtube-dl -g -f <format_id> <youtube-url>` 

Exp:omxplayer -o local --win 0,0,1280,720 `youtube-dl -g -f best <youtube-url>`
 ```

 無線網路(wifi)(etc/wpa_supplicant)
--------

在wpa_supplicant
建立home_wifi (可以隨意自己取名)
```
sudo nano /etc/wpa_supplicant/home_wifi
```
```
network={
ssid=”neworkname”
psk=”password”
}
```

設定無線網卡
> wpa_supplicant -i wlan0 -c /etc/wpa_supplicant/home_wifi &


啟動無線網卡

> dhcpcd wlan0


WIFI連接注意事項
---
如果router 本身具有網路連線防火牆等功能及需使用其wifi AP 的話 需注意DNS 的取得   
請參照 Arch Linux static Dns的設定

