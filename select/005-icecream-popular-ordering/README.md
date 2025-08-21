# 인기있는 아이스크림

## 문제 요약

- 테이블
  - **FIRST_HALF**: `SHIPMENT_ID`, `FLAVOR`, `TOTAL_ORDER`
- 요구 사항
  - 상반기에 판매된 아이스크림의 **맛(`FLAVOR`)** 을 조회
  - 정렬: `TOTAL_ORDER` **내림차순** → 동률 시 `SHIPMENT_ID` **오름차순**

## 정답 SQL

```sql
-- 상반기 아이스크림 맛을 주문량 내림차순, 출하번호 오름차순으로 정렬
SELECT
    FLAVOR
FROM FIRST_HALF
ORDER BY TOTAL_ORDER DESC, SHIPMENT_ID ASC;
```
