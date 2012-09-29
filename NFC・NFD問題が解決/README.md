「アリスとボブのGit入門レッスン」補足
=========================================

##NFC・NFD問題が解決（239ページ、13-09日本語ファイル名をgit addする）
* Git 1.7.12以降、濁点を含む日本語ファイル名もそのままgit addできるようになりました。
* 最新のGit 1.7.12.1をインストールして、以下の設定をして、git addの動作を確認しました。

````
$ cd ~
$ git init hello
$ cd hello
$ git config --local core.precomposeunicode true
$ touch お読みください
$ git add お読みください
$ git status
# On branch master
#
# Initial commit
#
# Changes to be committed:
#   (use "git rm --cached <file>..." to unstage)
#
#	new file:   お読みください
````

* リポジトリごとに`git config --local core.precomposeunicode true`の設定が必要になります。
* Git 1.7.12.1でgit initすると、リポジトリのデフォルトは以下の設定になっています。

```
$ git config --local -l
core.repositoryformatversion=0
core.filemode=true
core.bare=false
core.logallrefupdates=true
core.ignorecase=true
core.precomposeunicode=false
```

* 見てのとおり、リポジトリごとに__core.precomposeunicode=false__が設定されてしまうのです。
* そのため、__--global__設定で__core.precomposeunicode=true__を指定しても、無視されてしまいます。
* ただし、Git 1.7.12以前に作られたリポジトリに対しては__--global__設定も有効になると思われます。