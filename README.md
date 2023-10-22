# Laravel install
1. ビルドする
```
docker compose build --no-cache
```
2. コンテナを立ち上げる
```
docker compose up -d
```
3. appコンテナに入る
```
docker compose exec app sh
```
4. laravelをインストールする
```
composer create-project --prefer-dist laravel/laravel . "10.*"
```
5. [ここ](http://localhost) にアクセスし、Laravelのロゴ入りのトップページが表示されたら成功です！
注意: key:generateが必要な場合は、以下のコマンドを実行、もしくは[ここ](http://localhost)でkey:generateを実行してください

# データベースの作成
1. appコンテナに入る
```
docker compose exec app sh
```
2. src > .envの内容を以下に書き換えてください
```
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=website
DB_USERNAME=test
DB_PASSWORD=test
```
3. migrationを実行する
```
php artisan migrate
```
4. これが出てきたら成功です！
```
2014_10_12_000000_create_users_table ........................................ 274ms DONE
2014_10_12_100000_create_password_reset_tokens_table ........................ 196ms DONE
2019_08_19_000000_create_failed_jobs_table .................................. 116ms DONE
2019_12_14_000001_create_personal_access_tokens_table ....................... 196ms DONE
```
