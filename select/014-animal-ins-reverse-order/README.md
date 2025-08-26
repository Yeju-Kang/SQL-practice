# 역순 정렬하기

## 문제 요약

- 테이블
  - **ANIMAL_INS**: `ANIMAL_ID`, `ANIMAL_TYPE`, `DATETIME`, `INTAKE_CONDITION`, `NAME`, `SEX_UPON_INTAKE`
- 요구 사항
  - 동물 보호소에 들어온 모든 동물의 **이름(`NAME`)과 보호 시작일(`DATETIME`)** 조회
  - 정렬: `ANIMAL_ID` **내림차순(역순)**

## 정답 SQL

```sql
-- ANIMAL_ID 역순으로 이름과 보호 시작일 조회
SELECT
    NAME,
    DATETIME
FROM ANIMAL_INS
ORDER BY ANIMAL_ID DESC;
```
