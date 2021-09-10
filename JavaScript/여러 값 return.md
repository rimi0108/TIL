## 배열로 return 하기
```
const myCodes = function() {
    const a = 'hi'
    const b = 'hello'
    return [a, b]
}

const codes = myCodes();
const aCode = codes[0];
const bCode = codes[1];
```

- 배열 형태로 return 하여 배열의 인덱스에 접근하여 return값을 가져올 수 있다.

## 객체로 return 하기

```
const myCodes = function() {
    const a = 'hi'
    const b = 'hello'
    return {
        a : a,
        b : b
    }
}

const codes = myCodes();
const aCode = codes.a;
const bCode = codes.b;
```
- 객체 형태로 return하여 return값이 접근할 수 있다.
