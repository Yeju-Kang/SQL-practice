# 재구매가 일어난 상품과 회원 리스트 구하기

## 문제 요약

- 테이블
  - **ONLINE_SALE**: `ONLINE_SALE_ID`, `USER_ID`, `PRODUCT_ID`, `SALES_AMOUNT`, `SALES_DATE`
- 요구 사항
  - 동일한 회원(`USER_ID`)이 동일한 상품(`PRODUCT_ID`)을 **2회 이상 구매**한 경우 조회
  - 조회 컬럼: `USER_ID`, `PRODUCT_ID`
  - 정렬:
    1. `USER_ID` 오름차순
    2. `PRODUCT_ID` 내림차순

## 정답 SQL

```sql
-- 동일 회원이 동일 상품을 2회 이상 구매한 내역 조회
SELECT
    USER_ID,
    PRODUCT_ID
FROM ONLINE_SALE
GROUP BY USER_ID, PRODUCT_ID
HAVING COUNT(*) >= 2
ORDER BY USER_ID ASC, PRODUCT_ID DESC;
```
