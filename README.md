# Gitの勉強
- Gitは、バージョン(変更があるたびに更新される版名)管理を行うソフトウェア
- 最初にgitに自分の情報登録する。
git config --global user.name "${あなたの名前}"
git config --global user.email ${あなたのメールアドレス}
git config --global core.editor "vim"
git config -lで登録情報確認

- git clone git@github.com〇〇〇　GitHubのリポジトリをコピーして、自分のマシンの Linux 内にも GitHub のようなリポジトリを作る。
- git pull origin gh-pages リモートリポジトリの最新の情報を取得できる。
gh-pagesはブランチ。GitHub に push すると、GitHub Pages というサイトにWebページとしてリポジトリ内容が公開される。
- cat ファイル名　でローカルに取り込んだ内容を確認できる。
- git remote　現在登録されているリモートのリポジトリの一覧を見ることができる
- git add コマンドで、リポジトリに変更情報を追加する。このことをステージングと言う
git reset addでadd登録した情報を削除できる。
- git commit -m "〇〇"　コマンドで、リポジトリのインデックスに追加された変更情報にコメントを付けてコミットできる
- git push -u origin master コマンドで、ローカルのコミットをリモートのリポジトリに反映させることができる。-uオプは次回以降 origin(デフォリポジトリ名) と master(デフォブランチ名) を省略した時に、自動でこの値とするためのもの
- git initコマンドで、.gitディレクトリが作成される。この中にGitに関するすべてのデータが保存される。.git ディレクトリを丸ごと削除すれば、ローカルリポジトリを消去できる。
- tag　特定のコミットの状態に、別の名前をつけること。
1.0のtag作成の場合、git tag 1.0、git push --tags origin master　--tagオプがタグをpushするときのオプション
- README.md このファイルはGitHubでコードの説明や、画像を表示したり可能になる。
.mdはMarkdown 形式の文書ファイル

- git branch このリポジトリにどのようなブランチがあるかを、一覧表示するコマンド。masterはデフォ。git branch 〇〇で作成
ブランチはある時点のソースコードを分岐させて開発をしたもの。複数の異なる機能を並行して開発するときに必須。
- git checkout 〇〇でブランチの切り替え
- touch 〇〇.html などでファイル作成。VSで編集→→→ git add .(カレントディレクトリにある全てのファイル)→→git commit -m "見出し"→git push origin gh-pagesリモートリポジトリに push
- git merge 〇〇　ブランチの間で変更情報を取り込む→git push origin masterでリモートに取り込む

- 修正するときは直接作業はせず、新しくブランチをつくりそこへ修正内容を加える。
git branch 〇〇→→→VSなどで編集したファイルを git commit -am "コメント"でコミット
(-amオプは一度 git add してコミットしたことがあるファイルは、再度 git add しなくてもコミットに含めることができる。)→→git diff 〇〇　で違いを確認できる。→git merge 〇〇でマージしてgit
commitをする。コンフリクトが起きたらgit statusで確認。

