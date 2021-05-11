## 도서관의 도서 대출 관리

- 도서관에는 각 서고/서가에 많은 책들이 있다

- 고객들은 인터넷을 통해서 로그인한 후 도서 목록을 조회할 수 있다

- 고객들은 원하는 책을 대출 받을 수 있다.

- 고객은 책이 있을 경우 대출 예약을 할 수 있으며 대출을 위해서는 직접 방문해서 책을 찾아서 대출을 해야 한다

- 문장에서 -> 명사를 뽑고 의미상의 명사도 뽑는다 -> 마스터 테이블와 관계 테이블을 분류한다. 

# 도서관의 도서 대출 관리

- 마스터테이블

- 서고, 서가, 책

- 고객, 도서 목록

- 관계테이블

- 로그인, 조회, 대출(고객이 찾아서 대출받음), 대출 예약

<img src="http://drive.google.com/uc?export=view&id=1UlV1WRVYRLe4dKPVlt5WUGW-zCb8MJUo" width="500" height="500">

- 1번 이미지는 조상에게 물려받은 id를 참조만하고 독립적으로 PK를 구성하는 형태(독립형pk) -> 융통성 있는 구조 서고 없이 서가만 우선 등록이 가능 -> 문제가 발생할 가능성이 있음


<img src="http://drive.google.com/uc?export=view&id=1s4ANjLrSo2OI8UIDDBKOOty5Kb6xOANz" width="500" height="500">

- 2번 이미지 서고ID를 받아서  -> 서고 없이는 서가가 있을 수 없다. (상속형pk) -> 안전하게 관리하고 싶은 경우(엄격하게 관리됨 융통성이 없음)

- 상속형으로 갈 경우 table 깊이가 깊어 질 수록 pk가 하나씩 늘어남 

<img src="https://drive.google.com/file/d/1MydEDmP1HUe2xNohdpyCFdFPR1mYcfCl/view?usp=sharingz" width="500" height="500">

- PK가 너무 많아서 힘들 때는 보조키를 하나 만들어서 이를 참조할 때 사용하면 편리하다
![image](https://user-images.githubusercontent.com/79051105/117811793-f846da00-b29b-11eb-89b5-b09ef12ee289.png)








