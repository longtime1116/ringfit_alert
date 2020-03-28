# これは何
リングフィットアドベンチャーの在庫情報のサイトを定期的にチェックしてslackに通知するやつ

# 実行

```sh
export SLACK_WEBHOOK_URL="xxxxxx"
bundle install
bundle exec ruby app.rb
```

# デプロイ

```sh
heroku create --buildpack https://github.com/heroku/heroku-buildpack-ruby.git
git push heroku master
heroku run "bundle exec ruby app.rb"
```
