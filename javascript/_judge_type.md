# 型判定

## isNaN と Number.isNaN
- JavaScriptのグローバル関数の[isNaN](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/isNaN)は、対象の値がNaN(Not a Number)かどうかを true / false を返す。
- [Number.isNaN](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Global_Objects/Number/isNaN)の方がより堅牢

- NaNは非数を表しているが、`typeof`で確認すると`Number`型
- あくまで非数かどうかを確認するものなので、数値チェックなどには使わない方が良い

## lodashで判定
以下の関数が用意されている

- [isNumber](https://lodash.com/docs/4.17.15#isNumber)
- [isString](https://lodash.com/docs/4.17.15#isString)
- [isArray](https://lodash.com/docs/4.17.15#isArray)

他にもたくさんあるので[doc](https://lodash.com/)参照