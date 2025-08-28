# 동물의 아이디와 이름

## 문제 요약

- 테이블
  - **ANIMAL_INS**: `ANIMAL_ID`, `ANIMAL_TYPE`, `DATETIME`, `INTAKE_CONDITION`, `NAME`, `SEX_UPON_INTAKE`
- 요구 사항
  - 동물 보호소에 들어온 모든 동물의 **아이디와 이름** 조회
  - 조회 컬럼: `ANIMAL_ID`, `NAME`
  - 정렬: `ANIMAL_ID` 오름차순

## 정답 SQL

```sql
-- 모든 동물의 아이디와 이름을 ANIMAL_ID 기준으로 조회
SELECT
    ANIMAL_ID,
    NAME
FROM ANIMAL_INS
ORDER BY ANIMAL_ID ASC;
```
