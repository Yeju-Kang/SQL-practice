# 오프라인/온라인 판매 데이터 통합하기

## 문제 요약

- 테이블

  - **ONLINE_SALE**: `ONLINE_SALE_ID`, `USER_ID`, `PRODUCT_ID`, `SALES_AMOUNT`, `SALES_DATE`
  - **OFFLINE_SALE**: `OFFLINE_SALE_ID`, `PRODUCT_ID`, `SALES_AMOUNT`, `SALES_DATE`

- 요구 사항
  - 2022년 3월(`2022-03`)의 판매 데이터를 조회
  - 출력 컬럼: `SALES_DATE`, `PRODUCT_ID`, `USER_ID`, `SALES_AMOUNT`
  - 오프라인 판매의 경우 `USER_ID` 는 `NULL` 로 표시
  - 정렬:
    1. `SALES_DATE` 오름차순
    2. `PRODUCT_ID` 오름차순
    3. `USER_ID` 오름차순

## 정답 SQL

```sql
-- 2022년 3월 온라인/오프라인 판매 데이터 통합 조회
SELECT
    DATE_FORMAT(SALES_DATE, '%Y-%m-%d') AS SALES_DATE,
    PRODUCT_ID,
    USER_ID,
    SALES_AMOUNT
FROM ONLINE_SALE
WHERE DATE_FORMAT(SALES_DATE, '%Y-%m') = '2022-03'

UNION ALL

SELECT
    DATE_FORMAT(SALES_DATE, '%Y-%m-%d') AS SALES_DATE,
    PRODUCT_ID,
    NULL AS USER_ID,
    SALES_AMOUNT
FROM OFFLINE_SALE
WHERE DATE_FORMAT(SALES_DATE, '%Y-%m') = '2022-03'

ORDER BY
    SALES_DATE ASC,
    PRODUCT_ID ASC,
    USER_ID ASC;
```
