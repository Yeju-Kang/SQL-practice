# 강원도에 위치한 생산공장 목록 출력하기

## 문제 요약

- 테이블
  - **FOOD_FACTORY**: `FACTORY_ID`, `FACTORY_NAME`, `ADDRESS`, `TLNO`
- 요구 사항
  - 조건: `ADDRESS` 가 **'강원도'로 시작하는 공장**
  - 조회 컬럼: `FACTORY_ID`, `FACTORY_NAME`, `ADDRESS`
  - 정렬: `FACTORY_ID` 기준 오름차순

## 정답 SQL

```sql
-- 강원도에 위치한 공장 목록 조회
SELECT
    FACTORY_ID,
    FACTORY_NAME,
    ADDRESS
FROM FOOD_FACTORY
WHERE ADDRESS LIKE '강원도%'
ORDER BY FACTORY_ID ASC;
```
