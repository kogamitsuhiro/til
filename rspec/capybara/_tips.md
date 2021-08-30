# tips

## fill_inで空文字を入力する
編集モーダルなどでinput filedに入力するときは、前の値が入っている。
なので、以下のような感じで一度空文字を入力してから、変更後の値を入れる。

```ruby
fill_in 'name', with: ''
fill_in 'name', with: '変更後の値'
```
