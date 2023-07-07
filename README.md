# Linux演習

## 1. 基本操作

### 演習1-1

カレントディレクトリを「/usr/local/bin」に移動してください。

<br>

**＜期待結果＞**

```sh
[ec2-user@ip-172-31-4-68 ~]$ ※コマンド実行
[ec2-user@ip-172-31-4-68 bin]$
```

<br><br>

### 演習1-2

カレントディレクトリをログインユーザのホームディレクトリに移動してください。

<br>

**＜期待結果＞**

```sh
[ec2-user@ip-172-31-4-68 bin]$ ※コマンド実行
[ec2-user@ip-172-31-4-68 ~]$
```

<br><br>

### 演習1-3

カレントディレクトリのパスを表示してください。

<br>

**＜期待結果＞**

```sh
[ec2-user@ip-172-31-4-68 ~]$ ※コマンド実行
/home/ec2-user
```

<br><br>

### 演習1-4

カレントディレクトリに空のファイル `practice1.txt` を作成し、カレントディレクトリの内容を表示してください。

<br>

**＜期待結果＞**

```sh
[ec2-user@ip-172-31-4-68 ~]$ ※コマンド実行
practice1.txt
```

<br><br>

### 演習1-5

`practice1.txt`ファイルを `practice2.txt` という名前でコピーしてください。

<br>

**＜期待結果＞**　※ディレクトリの内容を表示した時

```sh
[ec2-user@ip-172-31-4-68 ~]$ ※コマンド実行
practice1.txt  practice2.txt
```

<br><br>

### 演習1-6

`practice2.txt` のファイル名を `sample.txt` に変更してください。

<br>

**＜期待結果＞**　※ディレクトリの内容を表示した時

```sh
[ec2-user@ip-172-31-4-68 ~]$ ※コマンド実行
practice1.txt  sample.txt
```

<br><br>

### 演習1-7

カレントディレクトリに `doc1`、`doc2` の2つのディレクトリを作成してください。

<br>

**＜期待結果＞**　※ディレクトリの内容を表示した時

```sh
[ec2-user@ip-172-31-4-68 ~]$ ※コマンド実行
doc1  doc2  practice1.txt  sample.txt
```

<br><br>

### 演習1-8

`sample.txt`ファイルを `doc1`ディレクトリに移動し、カレントディレクトリから `doc1`ディレクトリの内容を表示してください。

<br>

**＜期待結果＞**

```sh
[ec2-user@ip-172-31-4-68 ~]$ ※コマンド実行
sample.txt
```

<br><br>

### 演習1-9

`doc2`ディレクトリを削除してください。

<br>

**＜期待結果＞**　※ディレクトリの内容を表示した時

```sh
[ec2-user@ip-172-31-4-68 ~]$ ※コマンド実行
doc1  practice1.txt
```

<br><br>

### 演習1-10

`doc1`ディレクトリを内容も含めて削除してください。

<br>

**＜期待結果＞**　※ディレクトリの内容を表示した時

```sh
[ec2-user@ip-172-31-4-68 ~]$ ※コマンド実行
practice1.txt
```

<br><br>

### 演習1-11

viコマンドで `practice1.txt`ファイルに以下の内容を編集し、保存してください。その後、ファイルの内容を表示してください。

```
yamagata
toyama
yamanashi
wakayama
yamaguchi
Okayama
fukuoka
```

> コピペはNGです。

<br>

**＜期待結果＞**

```sh
[ec2-user@ip-172-31-4-68 ~]$ ※コマンド実行
yamagata
toyama
yamanashi
wakayama
yamaguchi
Okayama
fukuoka
```

<br><br>

### 演習1-12

viコマンドで `practice1.txt`ファイルの末尾に「Tokyo」と追記し、保存せずに閉じてください。その後、ファイルの内容を表示してください。

<br>

**＜期待結果＞**

```sh
[ec2-user@ip-172-31-4-68 ~]$ ※コマンド実行
yamagata
toyama
yamanashi
wakayama
yamaguchi
Okayama
fukuoka
```

<br><br>

### 演習1-13

`practice1.txt`ファイルの中で、「yama」を含む行を検索してください。

<br>

**＜期待結果＞**

```sh
[ec2-user@ip-172-31-4-68 ~]$ ※コマンド実行
yamagata
toyama
yamanashi
wakayama
yamaguchi
Okayama
```

<br><br>

### 演習1-14

`practice1.txt`ファイルの中で、大文字小文字を区別せず「oka」を含む行を検索してください。

<br>

**＜期待結果＞**

```sh
[ec2-user@ip-172-31-4-68 ~]$ ※コマンド実行
Okayama
fukuoka
```

<br><br>

### 演習1-15

`practice1.txt`ファイルの中で、「yama」から始まる行を検索してください。

<br>

**＜期待結果＞**

```sh
[ec2-user@ip-172-31-4-68 ~]$ ※コマンド実行
yamagata
yamanashi
yamaguchi
```

<br><br>

<hr>

## 2. ユーザー管理と権限

### 演習2-1

rootユーザーに切り替え、ユーザー `sample-user` を新規作成してください。その後、`/etc/passwd`の内容を表示してユーザーが追加されていることを確認してください。

<br>

**＜期待結果＞**

```
[ec2-user@ip-172-31-4-68 ~]$ ※コマンド実行
[root@ip-172-31-4-68 ~]# ※コマンド実行
（中略）
ec2-user:x:1000:1000:EC2 Default User:/home/ec2-user:/bin/bash
sample-user:x:1001:1001::/home/sample-user:/bin/bash
```

<br><br>

### 演習2-2

ユーザー `sample-user` のコメントを「The User for Test」に変更してください。その後、`/etc/passwd`の内容を表示してユーザー情報が更新されていることを確認してください。

<br>

**＜期待結果＞**

```sh
[root@ip-172-31-4-68 ~]# ※コマンド実行
（中略）
ec2-user:x:1000:1000:EC2 Default User:/home/ec2-user:/bin/bash
sample-user:x:1001:1001:The User for Test:/home/sample-user:/bin/bash
```

<br><br>

### 演習2-3

ユーザー `sample-user` に「sample001」というパスワードを設定してください。

<br>

**＜期待結果＞**

```sh
[root@ip-172-31-4-68 ~]# ※コマンド実行
Changing password for user sample-user.
New password:
Retype new password:
passwd: all authentication tokens updated successfully.
```

<br><br>

### 演習2-4

rootユーザーからログアウトし（ログインユーザーに戻り）、ホームディレクトリにある `paractice1.txt`ファイルの詳細情報を表示してください。

また、詳細情報を確認し、以下の内容がどうなっているかを説明しましょう。

- ファイルタイプ（ファイル？ディレクトリ？）
- 所有者
- 所有グループ
- 所有者の権限（読み取り、書き込み、実行のうち何が許可されている？）
- 所有グループの権限
- その他の権限

<br>

**＜期待結果＞**

```sh
[root@ip-172-31-4-68 ~]# ※コマンド実行
logout
[ec2-user@ip-172-31-4-68 ~]$ ※コマンド実行
-rw-rw-r-- 1 ec2-user ec2-user 61 Jul  6 11:06 practice1.txt
```

<br><br>

### 演習2-5

sudoコマンドを使用して `practice1.txt`ファイルを `/home`ディレクトリに移動してください。その後、ユーザー`sample-user`に切り替わり、`practice1.txt`ファイルの内容が表示できることを確認してください。

<br>

**＜期待結果＞**

```sh
[ec2-user@ip-172-31-4-68 home]$ ※コマンド実行
Password:
[sample-user@ip-172-31-4-68 home]$ ※コマンド実行
yamagata
toyama
yamanashi
wakayama
yamaguchi
Okayama
fukuoka
```

<br><br>

### 演習2-6

ログインユーザーに戻り、`practice1.txt`ファイルの権限を以下のように変更してください。なお、権限はrwxによる指定で変更してください。

- その他ユーザーから読み取り権限を削除する

権限変更後、詳細情報を表示してその他ユーザーの読み取り権限がなくなっていることを確認してください。

その後、ユーザー`sample-user`に切り替わり、`practice1.txt`ファイルの内容が表示できないことを確認してください。

<br>

**＜期待結果＞**

```sh
[sample-user@ip-172-31-4-68 home]$ exit
exit
[ec2-user@ip-172-31-4-68 home]$ ※コマンド実行
-rw-rw---- 1 ec2-user ec2-user 61 Jul  6 11:06 practice1.txt
[ec2-user@ip-172-31-4-68 home]$ su sample-user
Password:
[sample-user@ip-172-31-4-68 home]$ cat practice1.txt
cat: practice1.txt: Permission denied
```

<br><br>

### 演習2-7

ログインユーザーに戻り、`practice1.txt`ファイルの権限を以下のように変更してください。なお、権限は8進数による指定で変更してください。

- 所有者　－　読み取り、書き込み、実行
- 所有グループ　－　読み取り、書き込み
- その他ユーザー　－　読み取り

権限変更後、詳細情報を表示し、上記のとおり権限が設定されていることを確認してください。

<br>

**＜期待結果＞**

```sh
[sample-user@ip-172-31-4-68 home]$ exit
exit
[ec2-user@ip-172-31-4-68 home]$ ※コマンド実行
[ec2-user@ip-172-31-4-68 home]$ ls -l practice1.txt
-rwxrw-r-- 1 ec2-user ec2-user 61 Jul  6 11:06 practice1.txt
```

<br><br>

### 演習2-8

rootユーザーに切り替え、ユーザー `sample-user` をホームディレクトリを含めて削除してください。その後、`/etc/passwd`の内容を表示して `sample-user` が削除されていること、`sample-user` のホームディレクトリが削除されているを確認してください。

<br>

**＜期待結果＞**

```sh
[ec2-user@ip-172-31-4-68 ~]$ sudo su -
Last login: Fri Jul  7 02:04:01 UTC 2023 on pts/0
[root@ip-172-31-4-68 ~]# ※コマンド実行
（中略）
ec2-user:x:1000:1000:EC2 Default User:/home/ec2-user:/bin/bash
[root@ip-172-31-4-68 ~]# ls /home
ec2-user  practice1.txt
```

<br><br>