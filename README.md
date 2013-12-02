「アリスとボブのGit入門レッスン」サポート
=========================================

正誤リスト
----------

###13ページ 上から6行目 コミットID
（誤）bob-MacBook:demo bob$ git checkout __9de473b__ sample.txt

（正）bob-MacBook:demo bob$ git checkout __d7a8064__ sample.txt


###47ページ 上から10〜11行目 コミットID
（誤）__6348164__ "WhatIsGitにshowメソッドを追加"

（誤）__dbc6174__ "WhatIsGitクラスを追加"


（正）__8ed7ccc__ "WhatIsGitにshowメソッドを追加"

（正）__29814fe__ "WhatIsGitクラスを追加"


###54ページ 上から7行目 コミットID
（誤）[master __0d2b155__] ファイル名変更

（正）[master __e2ec12d__] ファイル名変更


###54ページ 下から9行目
（誤）試しに__ファイル名変更前に戻して__、git mvでやってみるね。

（正）試しに、git mvでやってみるね。


###54ページ 下から1行目 コミットID
（誤）HEAD is now at __7b9b252__ ファイル名変更

（正）HEAD is now at __e2ec12d__ ファイル名変更


###54ページ 下から2行目 末尾の記号
（誤）alice$ git reset --hard HEAD￣

（正）alice$ git reset --hard HEAD~


###55ページ 上から19行目 末尾の記号
（誤）alice$ git reset --hard HEAD￣

（正）alice$ git reset --hard HEAD~


###55ページ 下から10行目 コミットID
（誤）HEAD is now at __7b9b252__ ファイル名変更

（正）HEAD is now at __e2ec12d__ ファイル名変更


###56ページ 下から11行目 コミットID
（誤）__ec33455__ ファイル名変更

（正）__e2ec12d__ ファイル名変更


###56ページ 下から6行目 コミットID
（誤）HEAD＝最新のコミット(＝__ec33455__)

（正）HEAD＝最新のコミット(＝__e2ec12d__)


###80ページ 下から3行目 コミットID
（誤）git rebaseは、__5498a54__... showメソッドのメッセージを修正、で停止しています。

（正）git rebaseは、__6a4f43a__... showメソッドのメッセージを修正、で停止しています。


###81ページ 上から9行目 コミットID
（誤）ほら、最新のコミット＝HEADが「__cf9e7da__ "showメソッドのメッセージを修正"」

（正）ほら、最新のコミット＝HEADが「__6a4f43a__ "showメソッドのメッセージを修正"」


###111ページ 上から13行目 Ruby1.9.2以降の対応のため
（誤）`>> require 'what_is_git'`

（正）`>> require './what_is_git'`


###120ページ 下から15行目 Ruby1.9.2以降の対応のため
（誤）`>> require 'what_is_git'`

（正）`>> require './what_is_git'`


###141ページ 上から11行目

（誤）* Bob a73c7ab 式展開をするためダブルクォートへ変更

（正）* Bob a73c7ab __(origin/master, origin/HEAD)__式展開をするためダブルクォートへ変更


###170ページ 下から5行目
（誤）Delete tag '__Version-0.1__' (was __9ea7a9a__)

（正）Delete tag '__v0.1__' (was __d091ea1__)


###186ページ 下から1〜5行目
（誤）
````
*   Alice 7eab4a3 (master)対話の返答で日本語全角文字にも対応
| * Alice 8c71190 (HEAD, next)languageメソッドを追加
| * Alice f7af777 実行環境に合わせてデフォルト言語を設定する
|/
*   Alice b821e92 (v0.1)Merge branch 'master' of /Users/alice/Public/project
````
（正）
````
*   Alice 934f5cd (master)対話の返答で日本語全角文字にも対応
| * Alice 07c6f25 (HEAD, next)languageメソッドを追加
| * Alice d819640 実行環境に合わせてデフォルト言語を設定する
|/
*   Alice d091ea1 (v0.1)Merge remote-tracking branch 'origin/master'
````


###189ページ 上から1〜10行目
（誤）
````
alice$ git tree
*   Alice ce3fb50 (refs/stash)On next: 言語環境を取得する作業中
|\
| * Alice 260e6ee index on next: 8c71190 languageメソッドを追加
|/
*   Alice 8c71190 (HEAD, next)languageメソッドを追加
*   Alice f7af777 実行環境に合わせてデフォルト言語を設定する
| * Alice 7eab4a3 (master)対話の返答で日本語全角文字にも対応
|/
*   Alice b821e92 (v0.1)Merge branch 'master' of /Users/alice/Public/project
````
（正）
````
alice$ git tree
*   Alice ce3fb50 (refs/stash)On next: 言語環境を取得する作業中
|\
| * Alice 260e6ee index on next: 07c6f25 languageメソッドを追加
|/
*   Alice 07c6f25 (HEAD, next)languageメソッドを追加
*   Alice d819640 実行環境に合わせてデフォルト言語を設定する
| * Alice 934f5cd (master)対話の返答で日本語全角文字にも対応
|/
*   Alice d091ea1 (v0.1)Merge remote-tracking branch 'origin/master'
````


###272ページ 下から12行目 大文字から小文字へ
（誤）git verify-pack -v .__G__it/objects/pack/pack-of414439f64f968085208425de4

（正）git verify-pack -v .__g__it/objects/pack/pack-of414439f64f968085208425de4


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
