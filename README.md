# Restaurant_Crawler
- 맛집 사이트 크롤러 (다이닝코드)
- 2020 한이음
- 참조 : 블로그 링크


# v 1.01
- List_Crawler V 1.01 (Prototype) 구현

#### 문제점
1. 100개 이상 불러와도 91위 밖에 출력 안됨

2. 출력 결과에 광고가 섞여있음. 때문에 짧은 주소가 한줄씩 밀림

>10.쉑쉑버거/ 버거, 수제버거/ 강남역/ 줄서서먹는, 아메리칸스타일/ 서울특별시 강남구 역삼동 809-13 1층  
>강남본가가마골/ 광고가마골흑돼지 퀄리티있는 고기/ 청담동/ /  
>11.새벽집/ 육회비빔밥, 선지해장국/ 예술의전당/ 무한도전맛집, 연예인맛집/ 서울특별시 강남구 청담동 129-10

해결법
- .isdigit()를 통해 str[0]의 T/F 판별
- 10개 단위로 del arr[i] but IndexError: list assignment index out of range 각오해야함 (무식)

# v 1.02
- List_Crawler V 1.02 (Prototype) 구현

#### 문제점
1. short_address 밀림 문제 - 광고가 array에 포함되서 밀림
    - short_address array 삭제
    - long_address의 'OO구' 부분 추출 예정

2. 여전히 광고 출력
    - 해결법 v 1.01와 동일. but 프로토타입 수준이기에 보류

리스트 수집이 본 목적이 아니기에 코딩 보류하고 매장 상세정보 크롤링 계획