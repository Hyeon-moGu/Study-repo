# Database
<br>

## 데이터베이스 vs 파일시스템 

### 파일 시스템(File System)
**[장점]**
* data의 정의가 Application Program에 내포한다.
* 프로그램에서 데이터 접근하고 조작하는 것 이외에는 별도의 제어가 없다.

**[단점]**
* 데이터간 불일치 발생
* 동기화 X
* 쿼리언어 제공 X
* Recovery 기능 X
* 강제종료 등의 상황에 대처 기능 없음
* 데이터의 독립성이 없어 유지 보수 비용 높음
* 데이터 모델링 개념 부족
* 데이터 무결성 유지가 힘듬
* 데이터 공유의 어려움이 있어 생산성 낮음

### 데이터베이스 시스템(DataBase System)
파일 시스템의 단점을 보완해서 나왔다. <br>
데이터를 파일 단위로 저장하며 이러한 일들을 처리하기 위한 독립적인 응용프로그램과 상호 연동이 되어야한다. <br>
이때의 문제점은 데이터 종속성 문제와 데이터 무결성이다.
