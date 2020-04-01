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
  
  鍵の作成を行うと、「.pub」拡張子が付いている<strong>公開鍵</strong>と、付いていない<strong>秘密鍵</strong>が作成されます。
  公開鍵はSSHで接続したいサービスに登録しておくものです。
  
  作成された公開鍵のパーミッションを600に設定します。
  現在のパーミッションの確認
  <pre>
  % ls -la /Users/sbamboo/.ssh/id_rsa_github.pub
  -rw-r--r--   1 sbamboo  staff   746  4  2 01:57 id_rsa_github.pub<pre>
  パーミッションの変更
  <pre>% chmod 600 /Users/sbamboo/.ssh/id_rsa_github.pub</pre> 
  変更後のパーミッション確認
  <pre>
  % ls -la /Users/sbamboo/.ssh/id_rsa_github.pub         
  -rw-------   1 sbamboo  staff   746  4  2 01:57 id_rsa_github.pub</pre> 
  SSHのconfigファイル生成
  <pre>
  % vi /Users/sbamboo/.ssh/config
  </pre>
  <pre>
  Host github
   HostName github.com
   User git
   IdentityFile /Users/sbamboo/.ssh/id_rsa_github</pre>
   これにより<code>SSH github</code>と入力するだけで、ここで指定したホスト名、ユーザー名、秘密鍵が自動で指定されます。
