# DateTimeField

```python
2021-08-23 15:00:00.000000
```
- DateTimeField를 사용했을 때 위의 형식처럼 데이터가 들어가게 된다.

## 원하는 데이터만 뽑아오고 싶다!
```python
>>> project.end_date
datetime.datetime(2021, 11, 6, 0, 0, tzinfo=<UTC>)
```
- DateTimeField를 가지고 있는 객체의 필드를 가져오면 이런 형식으로 출력된다
### 날짜만 출력
```python
>>> project.end_date.date()
datetime.date(2021, 11, 6)
```
- date()를 이용하여 날짜만 뽑아올 수 있다.
### 시간만 출력
```python
>>> project.end_date.time()
datetime.time(0, 0)
```
- time()을 이용하여 시간도 출력이 가능하다.

### 해당 날짜의 요일 출력
```python
>>> project.end_date.weekday()
5
```
- 해당하는 날짜의 요일도 출력할 수 있다.
- 0:월, 1:화, 2:수, 3:목, 4:금, 5:토, 6:일

### 월, 일, 시, 분, 초, 마이크로초 개별 출력
```python
#월
>>> project.end_date.month
11
#일
>>> project.end_date.day
6
#시
>>> project.end_date.hour
0
#분
>>> project.end_date.minute
0
#초
>>> project.end_date.second
0
#마이크로초
>>> project.end_date.microsecond
0
```
- datetime 은 다양한 속성을 가지고 있다.
- 이 속성으로 원하는 데이터만 뽑아올 수 있다.
## 원하는 형식으로 출력하고 싶다!
### strftime method
```python
>>> project.end_date.strftime("%Y년 %m월 %d일")
'2021년 11월 06일'
```
```python
>>> project.end_date.strftime("%Y-%m-%d")
'2021-11-06'
```
```python
>>> project.end_date.strftime("%H시 %M분 %S초")
'00시 00분 00초'

```
- 위처럼 strftime 메서드를 이용하여 원하는 형식으로 출력할 수 있다.

## datetime module 사용
```
>>> from datetime import datetime
>>> datetime.now
<built-in method now of type object at 0x7fdd8ea0fc20>
>>> datetime.now()
datetime.datetime(2021, 8, 22, 7, 26, 36, 249828)
```
- datetime module을 import 해서 현재 datetime을 출력할 수 있다