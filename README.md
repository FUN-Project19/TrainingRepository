# TrainingRepository
## What is this?
Project19 Twitterプロジェクトにおいて、gitとGitHubの使い方を練習するために使用する仮のリポジトリになります。  
各自で実際にgitを用いてこのリポジトリを操作してみてください。

## Let's try it!
### ①Git環境を整えよう
#### ・開発環境に __Eclipse__ を利用している場合  
Eclipseを起動し、ツールバーの _Window_ から _Open Perspective_ を選び _Other_ を選択します。  
開いたウィンドウから _Git_ を選択して _OK_ を押します。  
Eclipseの右上にあるパースペクティブ一覧に __Git__ が表示されればOKです。  
![Imgur](http://i.imgur.com/46dtOXh.png)

#### ・開発環境に __Eclipse__ 以外を利用している場合
[Git for Windows](https://msysgit.github.io/) などをダウンロードして下さい。  

### ②リポジトリを __Clone__ しよう
__Clone__ とは、リモート（ウェブ上）のリポジトリを、ローカル（パソコン上）にコピーすることです。  

このリポジトリのURLはページ右下に表示されています。  
<https://github.com/FUN-Project19/TrainingRepository.git>  
URLをコピーして、EclipseのGit Perspectiveを表示します。  
![Imgur](http://i.imgur.com/fQ80vQE.png)  
Clone a Git Repository～ を選択して、URIの枠にコピーしたアドレスを貼り付けます。  
Branch Selectionはmasterを選択して _Next_ を押します。  
_Projects_ 欄の _Import all existing projects after clone finishes_ にチェックを入れて _Finish_ を押します。  
左側のGit Repositoriesタブに「TrainingRepository」が表示されれば成功です。

### ③新しく __Branch__ を作成しよう
__Branch__ とは、メインのソースコードを分岐させる作業です。  
元のソースにどんどん上書きしていくと、いざ突然別の作業が必要になった時戻るのが大変になってしまうのを防ぐ目的で使用します。  

先ほど追加された「TrainingRepository」を右クリックし、一番上の _Switch To_ メニューから _New Branch_ を選択します。  
Sourceに _master_ を選んであることを確認し、Branch nameに新しいbranch名を入力します。  
今回は自分の学籍番号を入力して、Checkout new branchにチェックが入っていることを確認してから _Finish_ を押して下さい。  
右上のパースペクティブから _Java_ を選択し、左側のNavigatorにTrainingProject [TrainingRepository b101****]が追加されていれば成功です。

### ④ソースコードを編集しよう  
EclipseでのJavaソースの編集作業は既存の知識とほぼ同じです。  
ソースを編集し、上書き保存をする点も全く一緒です。  
唯一違うのは、編集作業が一段落付いたところで __Commit__ という作業が必要な点です。  
__Commit__ とは、その時点までの編集内容をコメント付きで記録しておくことです。  
コミットは履歴としてすべて記録され、それぞれを相互に比較したりロールバックすることが可能です。  

試しに、TrainingProject -> src -> GitTraining -> training.java にあるソースコードを編集してみましょう。  
※今回はJavaの勉強ではないので以下のソースをコピペで構いません。  
引数xとyを加算した整数を戻り値するcalcメソッドを実装します。  
`return 0;` の部分を `return x+y;` に書き換えて下さい。  
また、mainメソッド内で3+4を計算して出力する部分を追記します。  
`System.out.printf("Hello World!\n");` の下に  
`String s = "3 + 4 = "+calc(3,4);`  
`System.out.printf(s);`
の2行を追加して下さい。  

編集を終えたら上書き保存をして、実行結果が
>Hello World!  
3 + 4 = 7  

となることを確認します。

### ⑤ソースコードをコミットしよう
編集作業が終了したら、編集内容をコミットします。  
上書き保存をした際に、左側のNavigator内の「TrainingProject」「src」「GitTraining」
「training.java」の4つのファイル名の先頭に＞が付いたことに気が付きましたか？  
これは、前回のコミットから変更があったファイルを示します。  
今回は一括でコミットするので大本になる「TrainingProject」を右クリックし、_Team_ から _Commit_ を選択します。  
一番上のCommit messageには、今回変更した内容を __誰が見ても分かりやすいように__ 説明する文を入力します。  
今回は
>calcメソッドを実装し、mainメソッド内で出力するようにした。

と入力することにします。  
下側のFilesでtraining.javaのチェックボックスが入っていることを確認したら _Commit_ を押します。  
コミット終了後、ファイル名の＞が消えたことを確認して下さい。  

### ⑥リポジトリを __Push__ しよう
__Push__ とは、ローカル上のリポジトリをリモートにアップロードすることです。  
今回、masterブランチは弄らずに新しいブランチで作業をしたので、プッシュを行うとGitHub上に新しいブランチが表示されるようになります。  
Eclipseの右上のパースペクティブから _Git_ を選択して、TrainingRepositoryを右クリックします。  
_Push Branch_ を選択してRemoteに _origin_ が選択されていることを確認し、_Next_ を押します。  
Loginを求められるので、GitHubのアカウントとパスワードを入力します。  
Message Detailsに赤文字のエラーが表示されなければ成功です。　　
その後自動的にリポジトリ全体のプッシュが行われるので、再度ログインを行うと完了します。
このページ（GitHubのウェブページです）を更新してみてください。  
![Imgur](http://i.imgur.com/CBghEBH.png)  
左上のbranch: masterとなっているボタンをクリックすると、先ほど追加された自分の学籍番号のブランチが表示されましたか？  
ブランチを切り替えると、表示されるソースコードも切り替わるはずです。  
TrainingProjectのフォルダの横に先ほどコミットした際のコメントが表示されていることに気が付きましたか？  
最新のコミット内容はこのように表示されるので、分かりやすいものを付けるようにしましょう。  
TrainingRepository/TrainingProject/src/GitTraining/training.java のソースページを開いた状態でブランチを切り替えると、元のモノと、新しいモノをそれぞれ表示できることを確認しましょう。  

### ⑦ブランチを __Merge__ しよう
__Merge__ は前述したとおり、異なるブランチを1つにまとめる作業です。  
各作業で新しく作成したブランチを、masterブランチに統合したり、子ブランチから派生した孫ブランチを子ブランチに統合しなおしたりする場合に使用します。  
基本的にこの作業は事前にチーム内で話し合いをしてから行って下さい。  
masterブランチを各自が勝手に行うと、突然の事態に対応できない事があるので作業は基本的に別ブランチ内で行って下さい。  

Mergeについては、後日リーダーに直接説明をすることになると思うため、ここでは説明を省略します。  

### トラブルが起きた！
Conflict（競合）などのトラブルは複数人作業に付き物です。  
Googleで検索をすれば解決策はいくらでも出てくるので各自で調べて解決してみるのもよいでしょう。  

## Usefle Links
[Git Documentation Gitの基本](https://git-scm.com/book/ja/v1/Git-%E3%81%AE%E5%9F%BA%E6%9C%AC)  
公式の解説集ですが、非常に分かりやすいです。  

[サルでも分かるGit入門](http://www.backlog.jp/git-guide/)  
項目ごとに使い方を図解して解説しているサイトなのでサルでも分かります（？）

[Shinpeim/introduction-to-git](https://github.com/Shinpeim/introduction-to-git/blob/master/README.md)
CUI版のGitの使い方を解説している、これまたGitHubのマークダウンで記述された解説サイトです。  
Eclipse以外で（特にLinux環境上で）開発する際には参考になると思います。
