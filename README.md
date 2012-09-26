「アリスとボブのGit入門レッスン」サポート
=========================================

正誤リスト
----------

###13ページ 上から6行目 コミットID
（誤）bob-MacBook:demo bob$ git checkout __9de473b__ sample.txt

（正）bob-MacBook:demo bob$ git checkout __d7a8064__ sample.txt


###54ページ 下から9行目
（誤）試しに__ファイル名変更前に戻して__、git mvでやってみるね。

（正）試しに、git mvでやってみるね。


###54ページ 下から2行目 末尾の記号
（誤）alice$ git reset --hard HEAD__￣__

（正）alice$ git reset --hard HEAD__~__


###55ページ 上から19行目 末尾の記号
（誤）alice$ git reset --hard HEAD__￣__

（正）alice$ git reset --hard HEAD__~__


コマンド履歴
------------

* 本文中で長くて手入力しづらいコマンドの履歴です。

###07-05
````
$ git log --graph --all --format="%x09%an%x09%h %d %s"
````
````
$ git help log
/The placeholders are:
````
````
$ git log --graph --all --format="%x09%C(cyan bold)%an%Creset%x09%C(yellow)%h%Cr eset %C(magenta reverse)%d%Creset %s"
````
````
$ git config --global alias.tree 'log --graph --all --format="%x09%C( cyan bold)%an%Creset%x09%C(yellow)%h%Creset %C(magenta reverse)%d%Cre set %s"'
````
````
$ alias tree='git log --graph --all --format="%x09%C(cyan bold)%an%Cr eset%x09%C(yellow)%h%Creset %C(magenta reverse)%d%Creset %s"'
````
###11-07
````
alice$ cp -r ../project ../project.back
````
````
alice$ git filter-branch --env-filter 'GIT_AUTHOR_EMAIL="alice@gitma il.com"' -- --all
````
````
alice$ git log --pretty=short
````
````
alice$ git filter-branch --commit-filter '
if [ "$GIT_AUTHOR_EMAIL" = "alice@example.com" ];
then
GIT_AUTHOR_EMAIL="alice@gitmail.com";
git commit-tree "$@";
else
git commit-tree "$@";
fi' -- --all
````
````
alice$ git log --oneline --all
````
````
alice$ git log --oneline --all --decorate
````
````
alice$ git reset --hard refs/original/refs/heads/master
````
````
alice$ git log --oneline --decorate
````
````
alice$ git filter-branch --commit-filter '
if [ "$GIT_AUTHOR_EMAIL" = "bob@example.com" ];
then
GIT_AUTHOR_EMAIL="bob@gitmail.com";
git commit-tree "$@";
else
git commit-tree "$@";
fi' -- --all
````
````
alice$ git filter-branch -f --commit-filter '
if [ "$GIT_AUTHOR_EMAIL" = "bob@example.com" ];
then
GIT_AUTHOR_EMAIL="bob@gitmail.com";
git commit-tree "$@";
else    
git commit-tree "$@";
fi' -- --all
````
````
alice$ git filter-branch --original refs/original_bob --commit-filter '
if [ "$GIT_AUTHOR_EMAIL" = "bob@example.com" ];
then
GIT_AUTHOR_EMAIL="bob@gitmail.com";
git commit-tree "$@";
else
git commit-tree "$@";
fi' -- --all
````
````
$ git for-each-ref --format="%(refname)" refs/original/ | xargs -n 1 git update-ref -d
````
````
$ paths=`git for-each-ref --format="%(refname)" refs/original/`
$ for path in $paths; do git update-ref "${path#refs/original/}" `cat ".git/${path}"`; done
````
````
$ git for-each-ref --format="%(refname)" refs/original/
````