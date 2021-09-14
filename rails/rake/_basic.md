# Rake
- Ruby もしくは Railsアプリケーションで人気のタスクランナー
- 先日 rake task 書いたのでメモ

### タスクの生成
```bash
rails g task greet
```
(基本的に既にタスクが生成されていることがあるので、生成するより、該当のnamespaceを探す方が多いとは思う)

以下のコードが生成される。
```ruby
namespace :greet do
end
```

### タスクの処理追加
```ruby
namespace :greet do
  task task_name: :environment do
    # 実行したい処理
  end
end
```

`task_name` は実行時に使用する。

DB操作する時は、普通に例外処理とか、トランザクションとか書くべき。

### 実行
```bash
rake greet:task_name
# rake namespace:task_name
```

