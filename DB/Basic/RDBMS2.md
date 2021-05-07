## 키의 정의

 - 하나의 테이블에서 각 레코드를 고유하게 식별할 수 있는 컬럼 또는 컬럼의 조합

 - 키의 조건은 NOT NULL, UNIQUE
 
 - 테이블 디자인 시 키를 정하고 테이블을 데이터베이스에 만들때 명시적으로 키를 선언함
 
 - 키는 키에 대응하는 인덱스 테이블에 생성됨
 
  - 인덱스 테이블은 키 값에 의해서 정렬되어 있음
 
 # 후보 키(Candidate Identifier)
 
 - 주 식별자가 될 가능성이 있는 식별자
 
 - 모든 식별자는 주 식별자가 될 수 있는 후보이므로, 식별자와 후보 식별자는 사실상 동일어
 
 - Determinant(결정자) : 이 값을 알면 나머지 속성 값도 알 수 있는 속성
 
 - 고객이 주는 데이터를 보통 주 식별자로 채택하지 않는다. 프로그램 내에서 키를 만들어 쓰는 것이 좋음 
 
 - ex) 주민번호, 고객명, 폰번호, 이메일, 집주소, 고객번호 : 위와 같은 경우 고객번호를 PK로 쓰고 주민번호, 폰 번호, 이메일 등을 후보키로 씀
 
 - NULL을 허용할 수 있다는 것이 주식별자와 다른점
 
 - 물리적으로 인스턴스의 유일성을 보장해주기 위해서 UNIQUE인덱스를 생성하는 것이 바람직하다.

# Primary Key(PK)

- 테이블 컬럼에서 각 레코드를 유일하게 식별할 수 있는 컬럼 또는 컬럼들의 집함

- 후보 키들 중에서 대표 키로 선정된 식별자
 
 - 최소한의 속성 조합이 주 식별자가 되도록 해야 한다.
 
 - 테이블 내의 각 레코드가 정확하게 식별되도록 보장한다.

 - 다양한 종류의 무결성을 설정하고 강화하는 것을 도와준다.

 - 테이블 관계를 설정하도록 해준다.
 
 # 칼럼 설명
 ![정수범위](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8488596ab1ea490ea5769a50acf8b9e9/670b4f45-578c-49f2-8931-eb041a69100a.png)
 ![소수범위](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8488596ab1ea490ea5769a50acf8b9e9/7025193b-2ded-4a3f-99c4-4fff1c64cf3c.png)
  
  - decimal 근사치를 허용하지 않고 4~16byte를 씀(화폐단위에서 많이 씀)
  
  - char(n) => string n자, 빈공간이 있을 경우 빈 공간 그대로 남아 있음
  
  - varchar[n] => 가변 길이 보통 50을 맞춰 높음 만약 'AB'만 쓸 경우 2바이트만 할당 됨
  
  - 기타 큰 문자 값은 생략했음 TEXT 등
   
  ![유니코드범위](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8488596ab1ea490ea5769a50acf8b9e9/632172ca-7822-4bc2-af4e-c9f98032f56e.png)
  
  ![날짜, 시간, 화폐범위](https://slid-capture.s3.ap-northeast-2.amazonaws.com/public/capture_images/8488596ab1ea490ea5769a50acf8b9e9/e3712dc9-e085-44ec-8e23-ebeaf2abdbf9.png)
  
  - 여러 화폐 단위를 지원할 경우 오류가 날 가능성이 있다고 함 쓰지 말자 
