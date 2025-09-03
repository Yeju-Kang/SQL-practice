# 가장 높은 판매가 조회하기

## 문제 요약

- 테이블
  - **PRODUCT**: `PRODUCT_ID`, `PRODUCT_CODE`, `PRICE`
- 요구 사항
  - 판매 중인 상품의 **최고 판매가**를 조회
  - 출력 컬럼명: `MAX_PRICE`

## 정답 SQL

```sql
-- 판매 중인 상품 중 가장 높은 판매가 조회
SELECT
    MAX(PRICE) AS MAX_PRICE
FROM PRODUCT;
```
