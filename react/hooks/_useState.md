# useState

## stateは1つのオブジェクトでまとめて管理すべきか、個別で管理すべきか
[参考: state 変数は 1 つにすべきですか、たくさん使うべきですか？](https://ja.reactjs.org/docs/hooks-faq.html#should-i-use-one-or-many-state-variables)

**結論: 状況によって違う**

> すべての state を 1 つの useState 呼び出しに含めても動作しますし、フィールドごとに別に useState を持たせることでも動作はします。しかしこれらの両極端の間でうまくバランスを取り、少数の独立した state 変数に関連する state をグループ化することで、コンポーネントは最も読みやすくなります。

特に理由がなければ個別で管理して、
まとめることによって管理しやすくあるのであれば、管理するという方針

まとめるなら以下のような感じ
```javascript
const [user, setUser] = useState({ firstName: 'soar', lastName: 'flat' });
```
個別管理なら

```javascript
const [firstName, setFirstName] = useState('soar');
const [lastName, setLastName] = useState('flat');
```
