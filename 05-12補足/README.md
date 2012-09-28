「アリスとボブのGit入門レッスン」補足
=========================================
##63ページ 下から2行目
* `git config --system`は、管理者権限で実行する必要があります。

````
$ sudo git config --system core.excludesfile /etc/gitexclude
error: could not lock config file /usr/local/git/etc/gitconfig: No such file or directory
````

* 上記エラーが発生する場合は、__/usr/local/git/etc/__を追加してください。
 * Gitのインストール環境によって、__etc__フォルダのパスは変化します。
 * インストール環境に合った__etc__フォルダを、追加する必要があります。

````
$ sudo mkdir /usr/local/git/etc/
Password:
````

* これで、`git config --system`が実行できるようになりました。

````
$ sudo git config --system core.excludesfile /etc/gitexclude
````

* 管理者権限でファイル出力するときには、注意が必要です。
 * 以下の例では`echo "file3"`の部分のみ、管理者権限で実行されます。
 * ファイル出力`>> /etc/gitexclude`は、通常権限の書き込みとなるため、エラーとなります。

````
$ sudo echo "file3" >> /etc/gitexclude
-bash: /etc/gitexclude: Permission denied
````

* ファイル出力まで管理者権限で実行するには、コマンド文字列として全体を渡す必要があります。

````
$ sudo sh -c 'echo "file3" >> /etc/gitexclude'
````

* 無事、書き込みできました。

````
$ cat /etc/gitexclude
file3
````