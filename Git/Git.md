新增 submodule

git submodule add git://github.com/majutsushi/tagbar.git .vim/bundle/tagbar

foreach 指令：

git submodule foreach --recursive git pull origin master

刪除 submodule


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

