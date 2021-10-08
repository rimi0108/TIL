# class
- 객체 지향 프로그래밍의 핵심

## 객체 지향 프로그래밍
- 프로그램을 객체들로 구성하고, 객체들 간 서로 상호 작용 하도록 작성하는 방법

## 객체란
- 객체란 영어로 object, 즉 사물을 뜻한다.
- 객체는 특정 로직을 갖고 있는 행동(method)와 변경 가능한 상태(멤버 변수)를 가진다.
- 원하는 구조의 객체 틀을 짜놓고, 비슷한 모양의 객체를 공장처럼 찍어낼 수 있다.
- 객체를 매번 만들어서 사용해도 좋지만, 큰 규모의 객체이거나 비슷한 모양의 객체를 계속 만들어야 한다면, class 라는 설계도를 통해 만들 수 있다.

```
let ray = {
    name: 'Ray',
    price: 2000000,
    getName: function() {
        return this.name;
    },
    getPrice: function() {
        return this.price;
    },
    applyDiscount: function(discount) {
        return this.price * discount;
    }
}
```
- 객체의 프로퍼티 값에는 함수도 넣을 수 있다.

```
const rayPriceByFunction = ray.getPrice();
console.log('함수로 접근 => ' + rayPriceByFunction)
```
- getPrice 함수는 위와 같이 접근할 수 있다.
- 객체 내부에서, 해당 객체의 프로퍼티에 접근하려면 `this`라는 키워드를 사용할 수 있다.
- 그래서 getPrice 메서드에서 this.price로 price 키에 접근할 수 있다.
- 코드에 새 객체를 추가하는데 프로퍼티는 똑같이 구성되어야 할 시 차마다 객체를 늘려나가서 코드가 길어지는 것이 아니라, 필요한 클래스를 생성하여 관리할 수 있다.