# スキーマ

## スキーマのmerge
- [参照](https://github.com/jquense/yup/issues/232)

```javascript
const schema1 = object({
  a: string(),
  b: array(),
});

const schema2 = schema1.shape({
  b: object(),
});
```
↑のようにmergeさせると、↓のようになる。
```javascript
const schema2 = object({
  a: string(),
  b: object(),
});
```