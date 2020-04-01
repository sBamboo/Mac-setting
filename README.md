# Mac-setting
<h1>Git設定準備</h1>
<ol>
  <li>Gitのバージョン確認</li>
    <pre>$ git --version
    git version 2.21.1 (Apple Git-122.3)</pre>
  <li>ユーザ情報登録</li>
    <pre>% git config --global user.name "ユーザ名"
    % git config --global user.email "メールアドレス"</pre>
  <li>ユーザ情報確認</li>
    <pre>
      % git config --list
      user.name=ユーザ名
      user.email=メールアドレス
    </pre>
</ol>

<style>
  pre{
  margin-bottom:0;
  }
</style>
