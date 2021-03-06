# vol.2 Git編

## Gitとは？
- プログラムのソースコードや文書の変更履歴を記録したり追跡したりするためのシステム。
- 上記のようなファイル管理のことをバージョン管理という。
- Githubは、Gitの仕組みを利用して、自分の書いた文書やプログラムを保存したりほかの人に公開したりできるようにしたウェブサービスのこと

## セットアップ
- OSがWindowsの場合、[git for windows](https://git-scm.com/)から、windows環境でgitを扱える一式をダウンロード
    - Git Bash: gitのbash（シェル）。インストールされた"git-bash.exe"は、gitのシェル用のコンソール（ターミナル）。git-bash.exeをつかったり、VSCodeのターミナルのシェルにgitbashを設定するなどして、各ターミナルソフトからのCLI操作・git操作が可能になる。
       - *(補足) シェルはユーザの入力をOS内部に伝える役割を持ち、ターミナルはそのシェルを実行するいわゆる「黒い画面」のことを指す。*
- 基本的なコマンド
    - `pwd`：自分が今いる場所を確認する
    - `mkdir[ディレクトリ名]`：ディレクトリを作る
    - `ls`：フォルダの一覧を表示する
    - `cd [ディレクトリ名]`：別のディレクトリに移動する 
- gitのユーザー設定
    - `git config --global user.email 'メールアドレス'`
    - `git config --global user.name '名前'`
- gitのプロキシ設定(プロキシを使用している場合)`
    - `git config --global http.proxy http://プロキシ名:ポート番号`
    - `git config --global https.proxy http://プロキシ名:ポート番号`
- ユーザー設定とプロキシ設定が完了したら、`git config --list`で正しく登録されているか確認

## ファイルのやり取り
- Gitの構造は、 `リポジトリ＞ディレクトリ＞ファイル`となっている
- リポジトリには、ローカルリポジトリとリモートリポジトリがある。ローカルリポジトリは自分のPC上でのみ編集や閲覧が可能。リモートリポジトリはウェブ上（Github）に置かれているもの。
- ローカルとリモート間でファイルを送りあうことができる。以下の指示はGitbash内で行う     
    【リモートリポジトリをローカルに持ってくる】
    1. `git clone [url]`：Github上のリポジトリのクローンがローカルに作られた
    1. `git pull`：リモートリポジトリのファイルをローカルリポジトリにコピー

    【ローカルで編集したファイルをリモートに載せる】
    1. `git add [対象]`：どれをセーブするのかを指定する。実行前にVSCode上での上書き保存が必要
    1. `git commit -m [コメント]`：どのような変更を行ったのかをコメントして保存する
    1. `git push`：変更をリモートに反映

## 補足
- VScodeからGithub内のリポジトリを編集するためには、  
    - Ctrl+O：ファイルを開く
    - Ctrl+K,O：作業ディレクトリを選ぶ（ここではWebmemoを選択）
    - Ctrl+B：編集するファイルを選ぶ
- VSCodeでターミナルを開く方法は[CTRL]+@
- コマンドで作業を行うときは、必ず、その作業を実行したい場所にいることが必要
    - だから、Pullを行うときは `cd [ディレクトリ名]`から行う必要がある      
