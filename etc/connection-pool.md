# Connection Pool
- 데이터베이스에 연결된 Connection을 미리 만들어 둔 후 Pool에 보관하였다가 필요할 때 Pool에서 Connection을 사용한 후 다시 Pool에 반환하는 기법
- Connection Pool을 사용하면 여러 Connection을 사용할 수 있기 때문에 더 큰 부하를 견딜 수 있다.
- 기존처럼 필요할 때마다 Connection을 생성하고 닫지 않아도 되기 때문에 어플리케이션의 성능 향상 또한 기대할 수 있다.

## Connection Pool 사용 방법
### 새로운 Pool 생성
```
mysql.createPool(_config)
```
### Pool에서 Connection 가져오기
```
pool.getConnection
```