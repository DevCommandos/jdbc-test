# JDBC

```
Java Database Connectivity
자바에서 데이터베이스에 접속할 수 있도록 하는 자바 api
```

## LOW LEVEL JDBC API를 사용해서 h2 디비로 CRUD를 구현해본다.


### SQL MAPPER
```
JdbcTemplate
MyBatis
SQL 까지 작성해야함.
```

### ORM
```
JPA 
구현체 : 하이버네이트, 이클립스링크
개발 생산성이 높아진다.  쉬운 기술은 아니므로 깊이있게 학습해야 한다.
```

# Connection Pool
```
요청 때 마다 커넥션을 얻으면 tcp/ip 통신이 계속 이루어지고
디비 내부에서도 세션을 만들고 이런저런 작업 완료 후에 커넥션이 만들어진다.

커넥션풀은 커넥션을 미리 다 만들어 놓고 빌려주고 반납하는 것이다.
이미 다 연결된 상태 및 세션도 만들어진 상태이므로 sql 전달하는 부분부터 수행하면 된다. 
```

# DataSource
```
커넥션을 얻을 때 
DriverManager로 직접 얻기 또는 커넥션풀에서 얻을 수 있다.
잘 운영하다가 갑자기 커넥션 얻는 방식을 변경한다면 어플리케이션 소스단을 수정할 수 밖에 없다.

그래서 javax.sql.DataSource라는 인터페이스를 제공한다.
커넥션을 획득하는 방법을 추상화
이 인터페이스의 핵심 기능은 커넥션 조회 하나이다.

DriverManager는 DataSource를 구현하지 않았다.
하지만 DriverManagerDataSource 제공해준다.
```

