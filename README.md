# これは何
リングフィットアドベンチャーの在庫情報のサイトを定期的にチェックしてslackに通知するやつ

# 実行

```sh
export SLACK_WEBHOOK_URL="xxxxxx"
bundle install
bundle exec ruby app.rb
```

# デプロイ


初回デプロイ

```sh
heroku create --buildpack https://github.com/heroku/heroku-buildpack-ruby.git
git push heroku master
heroku config:set SLACK_WEBHOOK_URL="xxxxx"
heroku run "bundle exec ruby app.rb"
```

スケジューラ登録

```sh
heroku addons:create scheduler:standard
heroku addons:open scheduler # このあと管理画面から設定
```

その他コマンド

```sh
heroku run bash
heroku logs --tail
```
