Yubikey

OATH-TOTP
===

OpenPGP
===
* default PIN 123456
* default Admin PIN 12345678

tools
---
* GPG2 (OpenPGP)

教學
---
```
首次須先修改Yubikey 密碼
gpg2 --card-edit
可以看自己的Yubikey OpenPGP資訊
之後輸入
>admin
>passwd

改密碼請修改PIN & Admin PIN


建立金鑰
gpg2 --export --full-gen-key

如果要備份
gpg2 --export-secret-subkey --armor (KeyWord) subkey
gpg2 --export-secret-key --armor (KeyWord) privatekey
gpg2 --export --armor (KeyWord)  publickey

建立子鑰
gpg2 --expert --edit-key (KeyWord)
>addkey
RSA (set your own capabilities) 2048/4096
Current allowed actions: Sign Encrypt
是開關式
選擇到剩下 authenticate capability

>Save


匯入
gpg2 --edit-key (KeyWord)
>toggle
>keytocard
回答1

選擇第一個subkey
>key 1 
>keytocard
只能回答2

取消選擇第一個子鑰，選擇第2個子鑰
>key 1
>key 2
>keytocard

只能回答3

>Save
```
PIV
===
* default PIN 123456
* default PUK 12345678
* default management key 010203040506070801020304050607080102030405060708

slots
---
[PIV certificate slots](https://developers.yubico.com/PIV/Introduction/Certificate_slots.html)

tools
---
* yubico-piv-tool
* pkcs15-tool ( OpenSC )

教學
---
```
修改PIN、PUK
還要修改 management key 建議下載軟體或參考官方做法
yubico-piv-tool -a change-pin -P 123456
yubico-piv-tool -a change-puk -P 12345678

建立金鑰
yubico-piv-tool -s 9a -a generate -o public.pem

驗證並自我簽名
yubico-piv-tool -a verify-pin -a selfsign-certificate -s 9a -S "/CN=SSH KEY/" -i public.pem -o cert.pem

匯入驗證
yubico-piv-tool -a import-certificate -s 9a -i cert.pem
```


```
可看自己有的PIV
pkcs15-tool --list-public-key
取得ssh鑰實
pkcs15-tool --read-ssh-key 01
```
Exp: ssh -I /.../opensc-pkcs11.so (Account@web.link)