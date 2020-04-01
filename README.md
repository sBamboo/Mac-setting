# Mac-setting
<h1>Git設定準備</h1>
<ol>
  <li>Gitのバージョン確認</li>
    <pre>
    $ git --version
    git version 2.21.1 (Apple Git-122.3)</pre>
  <li>ユーザ情報登録</li>
    <pre>
    % git config --global user.name "ユーザ名"
    % git config --global user.email "メールアドレス"</pre>
  <li>ユーザ情報確認</li>
    <pre>
      % git config --list
      user.name=ユーザ名
      user.email=メールアドレス</pre>
</ol>

<h2>SSH鍵の取得</h2>
<pre>
  % ssh-keygen -t rsa -b 4096 -C "S.bambooMK@gmail.com"
  Generating public/private rsa key pair.
  Enter file in which to save the key (/Users/sbamboo/.ssh/id_rsa):任意の鍵名をフルパスで記入
  Created directory '/Users/sbamboo/.ssh'.
  Enter passphrase (empty for no passphrase):パスフレーズを入力。必須ではないが入力を推奨
  Enter same passphrase again: 上記のパスフレーズの再入力
  Your identification has been saved in /Users/sbamboo/.ssh/id_rsa_github.
  Your public key has been saved in /Users/sbamboo/.ssh/id_rsa_github.pub.</pre>
