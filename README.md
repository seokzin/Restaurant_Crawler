# Restaurant_Crawler
- 맛집 사이트 크롤러 (다이닝코드)
- 2020 한이음
- 참조 : https://velog.io/@seokzin/series/%EC%9B%B9%ED%81%AC%EB%A1%A4%EB%A7%81


## v 1.01
- List_Crawler (Prototype) 구현

#### 문제점
1. 100개 이상 불러와도 91위 밖에 출력 안됨

2. 출력 결과에 광고가 섞여있음. 때문에 짧은 주소가 한줄씩 밀림

>10.쉑쉑버거/ 버거, 수제버거/ 강남역/ 줄서서먹는, 아메리칸스타일/ 서울특별시 강남구 역삼동 809-13 1층  
>강남본가가마골/ 광고가마골흑돼지 퀄리티있는 고기/ 청담동/ /  
>11.새벽집/ 육회비빔밥, 선지해장국/ 예술의전당/ 무한도전맛집, 연예인맛집/ 서울특별시 강남구 청담동 129-10

해결법
- .isdigit()를 통해 str[0]의 T/F 판별
- 10개 단위로 del arr[i] but IndexError: list assignment index out of range 각오해야함 (무식)

## v 1.02
- List_Crawler (Prototype) 에러 수정

#### 문제점
1. short_address 밀림 문제 - 광고가 array에 포함되서 밀림
    - short_address array 삭제
    - long_address의 'OO구' 부분 추출 예정

2. 여전히 광고 출력
    - 해결법 v 1.01와 동일. but 프로토타입 수준이기에 보류

리스트 수집이 본 목적이 아니기에 코딩 보류하고 매장 상세정보 크롤링 계획

## v 1.03
- Detail_Crawler (Prototype) 구현
- 매장 정보 추출까지만 구현

#### 문제점
1. 영업 시간이 정형화 되어있지 않음
    - 그대로 출력하거나 차선책을 찾아봐야 함

2. 이미지 최대 8개 크롤링
    - 더 크롤링 원하면 코드 자체 수정 필요

## v 1.04
- List_Crawler를 통해 Top100 맛집 URL 크롤링

#### 문제점
1. Detail_Crawler FindAll시 tuple 형식으로 저장되는데 이를 출력하기가 어렵

2. 이미지를 URL, IMG파일 어떤 형태로 저장할지 고민

3. 어떤 형태로 크롤링해야 DB 연동이 쉬울지 (백엔드 팀과 논의)

## v 1.05
- Detail_Crawler 출력부 구현 (text 출력)

#### 문제점
1. resizing된 이미지가 크롤링 됨  
    - 본래 목표하던 기능이기에 놔두기로 함. 만약 고친다면 url의 resized 부분을 제거한다?

2. 지금은 단일 사이트 크롤링이지만 top100 URL에 대해 크롤링 해야함
    - top100.txt 파일에 대해 한줄씩 input으로 받는 식으로 수정 가능. (추후)

3. txt 출력이 아닌 DB 저장에 용이한 형태(csv)로 출력부 수정해야함
    