
git reset 使用方式
---
                                       
以下列程序來表示流程圖    

### <font color="FF0000">A(Working)</font> --[add file]-->  <font color="00FF00">B(Staging)</font> --[commit]-->  C(Repo)


>git reset --soft  (SHA1 ID)

### 將 HEAD 到 (SHA1 ID) 所有的 "Repo變更記錄" 恢復成 <font color="00FF00">"Staging變更記錄"</font>
>git reset --mixed (SHA1 ID)       

### (預設) 將 HEAD 到 (SHA1 ID) 所有的 "Repo變更記錄 及 <font color="00FF00">Staging變更記錄</font>" 恢復成 <font color="FF0000">"Working 變更記錄"</font>
>git reset --hard (SHA1 ID)                 

### 將 HEAD 到 (SHA1 ID) 所有的 "Repo變更記錄 及 <font color="00FF00">Staging變更記錄</font> 及 <font color="FF0000">Working 變更記錄</font>" 全部消去

---
git Branch
---
使用 branch 可以自由切換/建立新分支

但當切換的目標是 (SHA1 ID) 時
會自動產生 "未命名"(暫時性) 的 branch

---
submodule
---
### 新增 submodule

git submodule add git://github.com/majutsushi/tagbar.git .vim/bundle/tagbar

foreach 指令：

git submodule foreach --recursive git pull origin master

### 刪除 submodule

git rm --cached /path/to/files
rm -rf /path/to/files


 [submodule ".vim/bundle/vim-gitgutter"]
   path = .vim/bundle/vim-gitgutter
   url = git://github.com/airblade/vim-gitgutter.git
-[submodule ".vim/bundle/vim-autoclose"]
-  path = .vim/bundle/vim-autoclose
-  url = git://github.com/Townk/vim-autoclose.git


git clone --recursive git@github.com:chinghanho/.dotfiles.git


git submodule init
git submodule update --recursive

