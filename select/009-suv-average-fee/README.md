# SUV 자동차 평균 대여 요금 조회하기

## 문제 요약

- 테이블
  - **CAR_RENTAL_COMPANY_CAR**: `CAR_ID`, `CAR_TYPE`, `DAILY_FEE`, `OPTIONS`
- 요구 사항
  - 조건: 자동차 종류(`CAR_TYPE`)가 `'SUV'`
  - 조회 컬럼: 평균 일일 대여 요금(`AVERAGE_FEE`)
  - 평균은 **소수 첫째 자리에서 반올림**
  - 컬럼명은 반드시 `AVERAGE_FEE` 로 지정

## 정답 SQL

```sql
-- SUV 자동차 평균 대여 요금 조회
SELECT
    ROUND(AVG(DAILY_FEE), 0) AS AVERAGE_FEE
FROM CAR_RENTAL_COMPANY_CAR
WHERE CAR_TYPE = 'SUV';
```
