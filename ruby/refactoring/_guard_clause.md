# ガード節
- 早期リターンのことは認識していたが、ガード節と呼ぶのは知らなかったのでついでに復習。

## 概要
- 他の言い方として、ガード構文・ガード条件などある
- 例外的な条件で例外的な値を返せる時、処理の冒頭にreturnすると、条件分岐のネストをひとつ浅くできる。

## リファクタリング例

リファクタリング前
```ruby
def invalid_permission?(user)
  if user.present?
    case user.permission
    when :admin, :owner
      false
    else
      true
    end
  else
    true
  end
end
```

リファクタリング後
```ruby
def invalid_permission?(user)
  return true if user.blank?

  case user.permission
  when :admin, :owner
    false
  else
    true
  end
end
```
