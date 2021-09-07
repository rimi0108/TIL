# async

- 함수 앞에 async 키워드를 추가하면 반환받는 값이 Promise가 된다.

```
let hello = async () => { return "Hello" };
```
## callback

// 자바스크립트는 동기적이다!
// 작성한 순서에 맞춰 동기적으로 실행된다
// hoisting: var, function 선언 가장 위로 올라가는 것
```
console.log('1');
setTimeout(() => console.log('2') , 1000);
console.log('3');
```
- 동기적 : 정해진 순서에 맞게 코드 실행
- 비동기적 : 언제 코드가 실행될지 예측 불가
- 자바스크립트 엔진은 코드를 제일 위에서부터 밑으로 실행한다.

### 콜백 함수
- 전달한 함수 나중에 불러줘!
- setTimeout

#### 동기적 콜백
printImmediately();

#### 비동기적 콜백
printWithDelay();

## json
- javascript object notation
- 데이터포맷
- {key:value} 형태
- 데이터를 주고받기에 가장 간단한 파일 포맷
- 프로그래밍 언어나 플랫폼에 상관없이 쓰일 수 있음

