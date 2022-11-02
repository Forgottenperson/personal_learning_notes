# git sign commit with Yubikey

確定這裡要有設定
```
git config user.name "name"
git config user.email "email"
```

設定gpg.exe程式路徑
```
git config gpg.program "gpg_link"
```

加入要簽署的GPG金鑰
global 為全域設定
```
git config user.signingkey "gpg_key_fingerprint"
or
git config --global user.signingkey "gpg_key_fingerprint"
```

加入 -S 後即可簽署
```
git commit -S -m "message"
```


有加入此內容即可不用加 -S
```
git config commit.gpgsign true
or
git config --global commit.gpgsign true
```


```
git commit -m "message"
```

之後把該GPG公鑰加入到gitlab/github上即可

之後便可在網頁上該欄位看到Verify

# git push commits with Yubikey

[先完成此做法](https://github.com/benpye/wsl-ssh-pageant)

完成其中的 How to use with WSL與 How to use with Windows 10 native OpenSSH client 設定

[再參照此作法](https://gist.github.com/matusnovak/302c7b003043849337f94518a71df777)

便能設定完成