GPG 常用整理
```
gpg gpg2
   --generate-key           產生新金鑰
   --full-generate-key      產生新金鑰(完整設定)

   -s --sign 產生檔案簽名
      --clear-sign 產生檔案明文簽名(文字)
    
   -e --encrypt   加密

   -d --decrypt   解密
      --verify    驗證簽名

   -k --list-keys 公鑰列表
      --fingerprint 金鑰指紋
   -K --list-secret-key 私鑰列表

      --delete-key 刪除公鑰
      --delete-secret-key 刪除私鑰

      --import 匯入金鑰

      --export 匯出金鑰

      --edit-key 編輯金鑰  trust 信任金鑰

      --sign-key 金鑰簽名  (使用金鑰 簽名 (公)金鑰)

      --card-status  硬體存放金鑰狀態
      --edit-card    編輯硬體存放金鑰

```
```
-a --armor              以 ASCII 碼 輸出
-r --recipient USER-ID  以 USER-ID  加密
-u --local-user USER-ID 以 USER-ID  簽名 或 解密

```

