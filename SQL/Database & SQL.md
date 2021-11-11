# Database & SQL
## Database
- 데이터베이스는 데이터를 저장하는공간이다.
  - 우리는 데이터를 메모리상에 저장할 수 있다. 하지만 휘발성이 높다.
  - 우리는 데이터를 파일이나 디스크에 저장할 수 있다. 영구 보관이 가능하다.

### RDBMS 
- 관계형 데이터베이스
- 2차원 테이블로 구성되어 있다.
- 컬럼, 로우로 구성되어 있다.
- 고유한 id, primary key(pk)를 가지고 있다.

### 테이블 사이 관계의 종류
- 일대일 One to One
- 일대다 One to Many
- 다대다 Many to Many
  - ex) 책은 여러 작가(공동 작가)에 의해 씌일 수 있고 작가들은 여러 책을 쓸 수 있다.
  - 중간 테이블이 무조건 필요하다.

#### 왜 Foreign key를 사용하나?
- Foreign key를 사용하지 않으면 관계에서 없는 값이 들어와도 오류가 나지 않는다.
  - ex) 일대일 관계에서 고객 정보 테이블에서 없는 고객 정보가 데이터에 들어오더라도 오류가 발생하지 않는다.

### Data Types
- 적절한 데이터타입을 정해주는 것이 중요하다.

#### Numeric
- int
- tinyint
- bigint
- float
#### Date/Time
- timeStamp
- date
- dateTime
#### Character/String
- char
- varchar
- text
#### Binary
- binary
#### Misc
- JSON(요즘 버전 데이터베이스에 존재)
- spatial (공간, 좌표 데이터)
- Enum(특수 케이스 데이터)

### CHAR vs VARCHAR
- CHAR를 사용하면 CHAR(100)으로 지정할 시 실제 데이터가 3이라도 데이터베이스 상에는 100만큼 자리를 차지한다.
- VARCHAR는 실제 데이터 사이즈 만큼만 차지한다.
- 그래서 CHAR는 데이터 길이가 고정되어 있을 때, VARCHAR는 데이터 길이가 변할 때 사용한다.
- CHAR의 장점은 VARCHAR보다 생성과 읽기가 약간 빠르다는 것이다.
- 하지만 대부분 인풋에 따라 변하는 데이터가 대부분이기 때문에 VARCHAR를 사용한다.

### DATETIME vs TIMESTAMP
- DATETIME은 일정 표현에 사용된다.
  - 생일 정보 => DATE
  - 식당 예약 기록 정보 => DATETIME
- TIMESTAMP는 어떤 이벤트가 일어난 목적을 기록할 때 사용된다.
  - created_at
  - updated_at

### DECIMAL vs FLOAT
- 둘 다 소수점 표현 가능
- FLOAT는 라운딩 에러가 발생할 수 있다.
- 금액 같은 정확한 값이 필요할 때는 DECIMAL을 사용하자

### ENUM
- 미리 정해진 값 리스트 중 하나만 데이터로 들어올 수 있다.
- 한 번 값을 정하면 바뀌지 않는 것을 가정해서 사용해야 하기 때문에 조심해서 사용해야 한다.
- ENUM 대신 One to One으로 사용하는 것이 확장성면에서 좋다.
