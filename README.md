# Githubフロー（forkパターン）

> ossなどに参加する際にfork&プルリクするパターンが一般的なので、このリポジトリは学習用として作成しています。

## 1. Fork する

GithubでForkしたいプロジェクトまで行って、右上にあるForkボタンを押します。今回、 [https://github.com/borderhub/demo.git](https://github.com/borderhub/demo.git) をForkします、私のGithubアカウントshirabelass1001上では [https://github.com/shirabelass1001/demo.git](https://github.com/shirabelass1001/demo.git)  というリポジトリが作成されます。

## 2. 自分のPCにcloneする

ターミナルでcloneしたいフォルダまで行って実行（そのフォルダ内にdemoという名前のフォルダが作成されます）

`$ git clone  https://github.com/your_name/demo.git`

## 3. branchを作る（新規ブランチ作成とそのブランチへの切りかえ）

`$ cd demo`

`$ git checkout -b [your_branch_name]`

## 4. ファイルを編集する

## 5. commit する

新規に作成したファイルの場合はgit addするのを忘れずに

`$ git commit -am '名前を追加'`

## 6. pushする

`$ git push origin [your_branch_name]`

4-6を繰り返す

## 7. upstream（Fork元リポジトリ）の設定

Forkした自分のリポジトリ (https://github.com/your_name/demo.git) は、Fork元のリポジトリ (https://github.com/borderhub/demo.git) の変更内容を自動更新しません。なので、Fork元のリポジトリの最新情報を自分のリポジトリに反映させる必要があります。

ここで、Forkした自分のリポジトリには、大抵デフォルト名としてoriginという名前がついています。新しくFork元のリポジトリにupstreamという名前をつけて追加しましょう。

`$ git remote add upstream  https://github.com/borderhub/demo.git`

## 8. Fork元リポジトリの最新を取得しlocalのmasterを更新

### branchをmasterに変更
`$ git checkout master`
### upstreamからpullして最新を取得
`$ git pull upstream master`
### localのmasterをoriginにpush（オプション）
`$ git push origin master`

## 9. branchをrebase

### branchを作成したbranchに変更
`$ git checkout [your_branch_name]`
### branchをrebase
`$ git rebase master`

## 10. branchをoriginにpush

`$ git push -f origin [your_branch_name]`

## 11. Pull Requestを作成

GithubでForkした自分のリポジトリ [https://github.com/your_name/demo.git](https://github.com/your_name/demo.git) に行き、左側にあるボタンよりbranchを[your_branch_name]に切り替えます。右上にあるPull Requestボタンを押して、Pull Requestを送信します。
