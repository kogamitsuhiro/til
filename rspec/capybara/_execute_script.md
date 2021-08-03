# execute_script
参考: rubydoc.info/github/jnicklas/capybara/Capybara%2FSession:execute_script

## 基本構文
```ruby
#execute_script(script, *args) ⇒ Object
```

## 用途
system testでjsを実行できる。

実際には、Date pickerでカレンダーを選択して入力フォームに値が入る場合など。

普通に書くと大変なので、jsで入力フォームに値を入れて、Date pickerによって入力した結果と同じものにする時など。

## 例
```ruby
today = Date.today.strftime('%Y/%m/%d')
page.execute_script("$('#user_birthday').val('#{today}')")
```