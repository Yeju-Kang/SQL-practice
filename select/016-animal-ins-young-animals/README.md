# 아픈 동물 찾기

## 문제 요약

- 테이블
  - **ANIMAL_INS**: `ANIMAL_ID`, `ANIMAL_TYPE`, `DATETIME`, `INTAKE_CONDITION`, `NAME`, `SEX_UPON_INTAKE`
- 요구 사항
  - 동물 보호소에 들어온 동물 중 `INTAKE_CONDITION = 'Sick'` 인 경우 조회
  - 조회 컬럼: `ANIMAL_ID`, `NAME`
  - 정렬: `ANIMAL_ID` 오름차순

## 정답 SQL

```sql
-- 아픈 동물의 아이디와 이름 조회
SELECT
    ANIMAL_ID,
    NAME
FROM ANIMAL_INS
WHERE INTAKE_CONDITION = 'Sick'
ORDER BY ANIMAL_ID ASC;
```
