# mysql-adminer

送られてきたダンプをチラ見する時のために書いておく。

## 使い方
### .envのコピーと環境変数の設定
```bash
cp .env.example .env
```

### 読み込むダンプの配置
```bash
cp SOURCE docker/data/SOURCE
```
*.sql, *.sql.gz を放り込んでおくとコンテナの初回up時に自動的にインポートされます。  
命名に際し制限はありませんが、複数のソースがある場合は昇順にインポートされます。

### Dockerコンテナの起動
```bash
docker compose up
```

### Adminerへアクセス
ポート番号は.envで変更可能です  
http://localhost:8080  

### ログイン情報 (初期値)
ユーザ名, パスワード, データベースは.envで変更可能です
- データベース種類: MySQL
- サーバ: mariadb
- ユーザ名: root
- パスワード: root
- データベース: mariadb

## 参考
### DataGripそのほかMySQLクライアントから接続する場合
```bash
HOST: localhost
PORT: 3306
USER: root
PASSWORD: root
DATABASE: mariadb
```
もし上記の設定で接続できない場合、HOSTをmariadbとしてください。