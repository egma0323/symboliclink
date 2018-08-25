# symboliclink_test
gitに登録されたシンボリックリンクをWindows10で扱うための確認用リポジトリ

## 確認環境
* エディション：Windows 10 Pro
* バージョン：1803
* OSビルド：17134.228

## Windows10でシンボリックリンクを扱う
1. git bushを管理者権限で起動
2. Windows10 git bushにて以下の設定を行う
```
$ git config --global core.symlinks true
```
3. clone
```
$ git clone https://github.com/egma0323/symboliclink_test
```
4. symboliclinkができていることを確認する
```
$ ll symboliclink_test/test1/
total 0
lrwxrwxrwx 1 egma 197121  8 8月  25 23:30 aaa -> ../test2/
lrwxrwxrwx 1 egma 197121 18 8月  25 23:30 aaa.txt -> ../test2/test2.txt
```

## その他確認
* WSL Ubuntu 18.04：
    - シンボリックリンクとして認識した
    - ubuntuでインストールしたgit上ではmodified扱い
    - windows側のgit.exe上ではmodifiedにはならなかった
* Docker for Windows CentOS7にvolumeでマウント
    - シンボリックリンクとして認識した

## 参考サイト
* [Git for Windowsでシンボリックリンクを扱えるようにする](https://qiita.com/ucho/items/c5ea0beb8acf2f1e4772)
