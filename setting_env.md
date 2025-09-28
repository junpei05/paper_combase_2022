# Dockerを用いたPython開発環境の構築

## 全体のフォルダ構成
<pre>
paper_combase_2022/
├── README.md
├── 0_example
│   ├── Dockerfile
│   ├── requirements.txt
│   └── california_housing.ipynb
├── 1_・・・
│   ├── Dockerfile
│   ├── requirements.txt
│   ├── ...
├── 2_・・・
└── 3_・・・
</pre>

- **For uploading a large file.md**  
  25MB以上のサイズのファイルをアップロードするための手順。
- **Dockerfile**  
  Dockerイメージを構築するための設定ファイル。必要なライブラリのインストールをまとめて記述。
- **requirements.txt**  
  Pythonライブラリのインストールに使用するファイル。
- **california_housing.ipynb**  
  ボストン住宅価格を題材にした回帰分析サンプルNotebook。

---
## Dockerで作成したコードのローカルPCでの実行
1. あらかじめ、Docker Desktopをインストールしておく

2. Githubにログインする
``` zsh 
gh auth login
```

3. リポジトリをダウンロードする  
   ローカルにgitのインストールが必要です(この手順はFor uploading a large file.md冒頭参照)。
``` zsh 
git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY
```

4. 動かしたいコードがあるファイルにディレクトリを変更する  
   Dockerfileがあるディレクトリまで順々に変更する。
   もしディレクトリ名にスペースを用いていたら、"(ダブルクオテーション)で括る。  
``` zsh 
cd YOUR_REPOSITORY
cd 0_example
git lfs pull #該当フォルダに25MB以上のファイルがある場合は実行してください。もしエラーが出たら、GitLFSをダウンロードする必要あるかもです。
```

5. Docker Desktopを開く
``` zsh 
open -a Docker
```  

6. Docker imageを作成する  
  **Dockerfileの拡張子が.txtになっていた場合注意！拡張子を消してください**  
``` zsh 
Docker build ./ -t "Docker imageの名前（自分で決めて設定）":latest
```

7. Docker imageを起動する  
``` zsh 
Docker run -p 8888:8888 "6で決めたDocker imageの名前":latest
```

8. コマンド実行時に表示されたhttp://127.0.0.1:8888/tree?token=... のようなURLをコピーしてブラウザで開く。  
   もしくは、localhost8888:8888をブラウザに入力する。
