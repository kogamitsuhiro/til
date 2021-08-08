# mailcatcher

`letter_opener`だとrails アプリに組み込む必要があるが、`mailcatcher`は単独で動作させることができる。

インストール
```bash
$ gem install mailcatcher
```

```ruby
# rails側設定
config.action_mailer.delivery_method = :smtp
  config.action_mailer.smtp_settings = { address: 'localhost', port: 1025 }
```

smtpサーバー起動
```bash
$ mailcatcher
```
