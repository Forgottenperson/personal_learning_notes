安裝Arch Linux
====================
[UEFI+GPT的Arch Linux安裝步驟(似乎有少寫請參考下面的連結)](http://note.kurodigi.com/archlinux-uefi-install/)  
[P.S.請參考這個網頁的mkinitcpio](http://www.wlintmp.net/2014/02/arch-linux.html)  

註記 base-devel,

---

安裝Arch Linux後
========================

### 接下來安裝桌面環境，也可以不裝，再裝之前請先務必確認你已經有建立新的使用者，並有用visudo 來完成為這位新使用者給予root權限
#### 以下為pacman -S 軟體名稱

圖形介面
--------------------------
xorg-server xorg-server-utils(xorg-apps) xorg-xinit  

顯示驅動程式(擇一)
--------------------------
AMD- xf86-video-amdgpu  
Intel- xf86-video-intel  
Nvidia- xf86-video-nouveau

VMware- open-vm-tools
        xf86-video-vmware
        xf86-input-vmmouse
        vmtoolsd.service(enable)

登入圖形管理(擇一(自己都用括弧起來的))
--------------------------
KDE Plasma 5 - sddm  
KDE4 -kdm  
GNOME - gdm  
LXDE -lxdm  
Universal Display Managers - lightdm  
mdm-display-manager,(slim),xorg-xdm  


桌面管理(擇一)
--------------------------
KDE Plasma 5 -plasma  
Cinnamon- cinnamon  
gnome - gnome  
LXDE -lxde  
MATE -mate  
XFCE -xfce4  
i3(i3-wm)-i3
i3-gaps

桌面管理應用程式(擇一)
--------------------------
KDE Plasma 5 -kde-applications  
Cinnamon- N/A  
gnome - gnome-extra  
LXDE -N/A  
MATE -mate-extra  
XFCE -xfce4-goodies  


圖形化terminel終端機(擇一或自己找)
--------------------------
gnome-terminal  

rxvt-terminal


網路管理器(可裝也可不裝)
--------------------------
pacman -S networkmanager  

安裝網路管理服務的UI  

pacman -S network-manager-applet  

無線網路  

安裝無線工具  

pacman -S wireless_tools  

wpa_supplicant安裝，


systemctl disable dhcpcd.service  


systemctl enable NetworkManager.service  


---

無線網路(wifi)(etc/wpa_supplicant)
--------

在wpa_supplicant
建立home_wifi (可以隨意自己取名)

> sudo nano /etc/wpa_supplicant/home_wifi

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


佈景主題(可裝也可不裝)
--------------------------
Minty  
New-Minty  
Adwaita-dark  
elementary

* compiz(adwaita)
* conky conky2 Conky-Colors(系統環境詳細資訊)
* cairo-docky { Numix[GTK2] Numix-Circle-Light } && Docky(Plank)
---
* (i3-gaps)
* Ranger
* Polybar-Font Awesome-RobotoMono
* Arc-theme 
* Rofi -Sardi-Mono
* Dunst
* betterlockscreen
* Pywal 
---

建議安裝程式(可裝也可不裝)
--------------------------
以下為pacman -S 軟體名稱(P.S 升級系統為 pacman -Syu)  
* screenfetch  
* wget、curl
* git
* smplayer
* omxplayer  (ARM)推薦
---
下面這個建議是用 bash *.sh 來安裝，檔案請到該官網去下載  
jupyter-notebook  

-------------------

(中文)語言介面與輸入法
---

    使用繁體中文，可將下列內容寫入~/.config/locale.conf

    LANG="zh_TW.UTF-8"



    字形
    pacman -S ttf-droid


    fc-cache -v


設定XIM環境變數


    export GTK_IM_MODULE=ibus
    export XMODIFIERS=@im=ibus
    export QT_IM_MODULE=ibus

安裝輸入法

    pacman -S ibus

    pacman -S ibus-pinyin ibus-libpinyin 




    ibus-setup

    將下列內容寫入家目錄下的.xinitrc

    ibus-daemon -xrd



----

mate 桌布背景幻燈片設定 [原github](https://github.com/robertmodesty/make-slideshow-wallpaper/blob/master/mksldshw)


請在官網的AUR找出以下套件的 (PKGBUILD)
* package-query  
* yaourt  


#### AUR 請依照下面的順序安裝 yaourt套件
```
	git clone https://.../X.git
	cd .../X
	makepkg -si (要有PKGBUILD) 基本會再 git 裡 沒有的話再找找
```

	makepkg -si (要有PKGBUILD)
	可以拆解成

```
	makepkg -s PKGBUILD
	pacman -U *.pkg.tar.xz
```

### yaourt 完成後請輸入此格式來安裝(yaourt -S 軟體名稱)
---
以下為AUR套件 必須要用 yaourt 請確認有裝好 yaourt -S 軟體名稱  
* Visual Studio Code


部分功能說明
===============================
ssh
----
```
在自己的家目錄下建立 ~/.ssh/authorized_keys 將公鑰放入並以行區分
.ssh 權限 700
authorized_key  權限 600

連接登入時
ssh -i (要使用其私鑰登入的路徑或名稱) Account@ip  
// 選擇要登入的帳戶@找到對方的 IPv4 或 IPv6 的位置 

```
ssh Tunnel
---
```
//本地機器連到遠端機器
ssh -L (本地的Port):(遠端的(Local address)):(遠端的(Local address)的Port)  (遠端帳戶):(遠端ip位址)
//遠端機器連回本地機器
ssh -N -R (遠端的Port):(本地位址(localhost)):(本地位址的Port)   (遠端ip位址)
```
使用者新增
---
```
useradd -m -g users -s /bin/bash {Name}
-m 為這個使用者建立資料夾
-g 設定群組 users
-s 設定shell
```
---

背景執行
---
```
在該 command 最後加上 &

查詢當下背景執行的 command
> jobs

已經執行的 command 放入倍警
Ctrl+Z 暫停
> bg %(number)

把背景的工作切換到前面
> fg %(number)

登出不停止工作
> nohup 
```

靜態DNS(WIFI)
----
```
dhcpcd
需要設定成靜態DNS的時候
/etc/dhcpcd.conf
---
static domain_name_servers=8.8.8.8 8.8.4.4


在
/etc/resolv.conf
可以看到取得的 DNS

```