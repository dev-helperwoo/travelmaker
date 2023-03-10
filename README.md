# 호텔 예약 시스템 API
## API 요구사항
```
    1. 호텔을 등록 할 수 있어야 한다. (단, 호텔별 객실 수량은 지정할 수 있어야 한다)
    2. 호텔 리스트를 볼 수 있어야 한다.
    3. 호텔 숙박 예약 신청이 가능해야한다.
    4. 예약 신청 시 숙박일자는 지정하지 않아도 되며 하나의 예약이 하나의 재고로 판단되어야 한다.
       (일자에 대해서는 신경쓰지 않아도 됨)
    5. 솔드아웃 되면 호텔 리스트는 볼 수 있지만, 해당 호텔이 솔드아웃임을 알 수 있어야 한다.
    6. 솔드아웃 된 호텔은 예약이 불가능해야 한다.
    7. 예약 신청된 건에 대해 확정 및 거절(반려) 처리를 할 수 있어야 한다.
    8. 확정 됐다면 호텔 재고가 줄어든 것으로 판단 할 수 있어야 한다.
    9. 거절(반려) 처리되면 예약
       은 취소된다.
```

## 개발환경
```
    ┌─ docker-compose
    ├── php:8.1
    ├── nginx
    └── mysql:8.0
```

## 실행
```
    $ docker-compose up -d
```

## API 문서
- darkaonline/l5-swagger 패키지를 활용한 Swagger 문서에 기술
- [Swagger 문서](http://localhost/api/doc)
```
    - L5-Swagger 구성
    $ php artisan vendor:publish --provider "L5Swagger\L5SwaggerServiceProvider"
    
    - L5-Swagger 생성
    $ php artisan l5-swagger:generate
    
    - Swagger UI path
    /api/doc
``` 

## API 목록
```
    - 호텔 목록: [GET] /api/hotel
    - 호텔 등록: [POST] /api/hotel
    - 예약 목록: [GET] /api/reservation
    - 예약 등록: [POST] /api/reservation
    - 예약 수정: [PATCH] /api/reservation/{id}
```