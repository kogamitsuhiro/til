# shared_XXX

## shared_examples / shared_examples_for / shared_context の違い
メソッド名が違うだけで、処理は同じ。

https://github.com/rspec/rspec-core/blob/master/lib/rspec/core/shared_example_group.rb#L100-L101

```ruby
alias shared_context      shared_examples
alias shared_examples_for shared_examples
```
