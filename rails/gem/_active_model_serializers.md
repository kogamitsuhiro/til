# active_model_serializers
シリアライズを別のモデルに移すことができる。

[公式doc](https://github.com/rails-api/active_model_serializers/blob/v0.10.6/docs/general/serializers.md)


## 使用例
`app/serializers` 配下にモデルを書く。
```ruby
class Api::V1::HogeSerializer < ActiveModel::Serializer
  attributes(
    :id,
    :name,
    :company_id,
  )
end
```

controllerで、jsonを返すときにシリアライザーを指定。
```ruby
def show
  render(
    json: @user,
    serializer: Api::V1::HogeSerializer
  )
end
```