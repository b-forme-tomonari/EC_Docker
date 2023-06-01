# EC_Docker
## 概要
Spring BootとThymeleafを使用したECサイトをDockerで動作するようにしたものです。

## コンテナ構成
Dockerコンテナ構成は以下の通りです。
|概要|詳細|ポート番号|
|:--|:--|:--|
| Java開発キット | OpenJDK（ver:11）||
| ウェブサーバー | nginx（ver:latest）| 80 |
| アプリケーションサーバー | Tomcat（ver:9.0.50）| 8080 |
| データベースサーバー | MySQL（ver:8.0.26）| 3306 |
| セッションサーバー | Redis（ver:6.2.5）| 6379 |

## Windowsでの実行方法
1. このレポジトリを任意の場所にダウンロードします。

2. コマンドプロンプトでcdコマンドでダウンロードしたフォルダに移動します。

3. dockerが起動していることを確認してから、以下のコマンドでコンテナをビルドします。
   ``` sh
   docker-compose build
   ```
   
4. 以下のコマンドでコンテナを起動します。
   ``` sh
   docker-compose up -d
   ```
   
5. 以下のコマンドでコンテナを終了します。
   ``` sh
   docker-compose down
   ```
## ユーザー一覧
ECサイトにログインできるユーザーは以下の通りです。
|ユーザーID|パスワード|権限|
|:--|:--|:--|
| admin | admin | 管理者 |
| general | general | 一般 |


## フォルダ構造
フォルダ構造は以下の通りです。
``` sh
EC_Docker
│  docker-compose.yml
│
├─java
│      Dockerfile
│
├─mysql
│  │  Dockerfile
│  │
│  ├─conf.d
│  │      mysql.cnf
│  │
│  └─sql
│          V1__user_info.sql
│          V2__goods_info.sql
│          V3__role.sql
│          V4__purchase_history.sql
│          V5__billing_address.sql
│
├─nginx
│  │  Dockerfile
│  │
│  ├─conf.d
│  │      nginx.conf
│  │
│  └─logs
├─redis
│      Dockerfile
│
└─tomcat
    │  Dockerfile
    │
    ├─logs
    └─webapps
            ec.war
 ```
    

   

