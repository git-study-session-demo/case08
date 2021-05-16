# バグったコミットを見つけ出す

> バグを発見する時、いつからのバグなのか、を効率的に探し方法

# 0. リポジトリを作成しよう

### フォークする
<img width="1149" alt="スクリーンショット 2021-05-17 1 45 51" src="https://user-images.githubusercontent.com/869103/118405253-edcc7c00-b6b1-11eb-88c1-e031cd51cf5f.png">

### クローンする
<img width="1170" alt="スクリーンショット 2021-05-17 1 46 00" src="https://user-images.githubusercontent.com/869103/118405263-f4f38a00-b6b1-11eb-95db-e367c653c0b4.png">

```
git clone <リポジトリURL>
```

# 1. バグを確認する
```
cd case08
open index.html
```

# 2. バグを探し範囲を決める
```
git log --pretty=oneline
```

### 今回は最初から最後までをバグ探す範囲としますので、この二つのコミットIDをメモする
<img width="796" alt="スクリーンショット 2021-05-17 1 49 17" src="https://user-images.githubusercontent.com/869103/118405326-65021000-b6b2-11eb-999d-2ea95f4f7457.png">

# 3. バグ探しを開始する

```
git bisect start <最後のコミット> <最初のコミット>
```
### 途中で動作確認し、その結果をgitに教えてあげる
```
git bisect <goodかbad>
```
# 4. バグを見つけたらその中身を確認する
```
git show <バグのコミットid>
```

# 5. バグ探しを終了する
```
git bisect reset
```
