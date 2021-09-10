# formikなしで、yup単体で使う方法

formikのvalidation schemaでyupを使うケースが多いが、yup単体で使用したのでメモ。

[公式doc](https://github.com/jquense/yup)

## 使い方
公式docに書いているけど、一応書いとく。

```javascript
// now use Yup schemas AFTER you defined your custom dictionary
let schema = yup.object().shape({
  name: yup.string(),
  age: yup.number().min(18),
});

schema.validate({ name: 'jimmy', age: 11 }).catch(function (err) {
  err.name; // => 'ValidationError'
  err.errors; // => ['Deve ser maior que 18']
});
```

```javascript
// schema.validate(対象のオブジェクト)
```
