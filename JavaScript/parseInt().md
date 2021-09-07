## parseInt()
- 문자열 인자를 숫자로 변경할 수 있다.

```
function roughScale(x, base) {
    const parsed = parseInt(x, base);
    if (isNaN(parsed)) { return 0; }
    return parsed * 100;
}
```
### 구문
> parseInt(string, radix);
- string
  - 숫자로 변환할 문자열
- radix
  - optional
  - string 문자를 읽을 진법
  - 2~36 사이의 수
- 리턴값
  - string을 정수로 변환한 값을 리턴
  - string의 첫 글자를 정수로 변환할 수 없다면 NaN(Not a Number) 리턴
    - 문자열의 첫글자가 숫자가 아닐때, ex) k10, ""