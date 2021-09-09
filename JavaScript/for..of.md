## for...of
- for...of 명령문은 반복가능한 객체(Array, Map, Set, String, TypedArray, arguments) 에 대해서 반복하고 각 개별 속성값에 대해 실행되는 문이 있는 사용자 정의 반복 후크를 호출하는 루프를 생성한다.

```
const array1 = ['a', 'b', 'c'];

for (const element of array1) {
  console.log(element);
}

// expected output: "a"
// expected output: "b"
// expected output: "c"

```

```
let iterable = [1, 10, 20];

for (let value of iterable) {
    console.log(value);
}
```
> 1
> 10
> 20

## for..in 과 for..of 의 차이
- for..in
  - 객체 순환
- for..of
  - 배열 순환
