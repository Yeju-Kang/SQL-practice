# 여러 기준으로 정렬하기

## 문제 요약

- 테이블
  - **ANIMAL_INS**: `ANIMAL_ID`, `ANIMAL_TYPE`, `DATETIME`, `INTAKE_CONDITION`, `NAME`, `SEX_UPON_INTAKE`
- 요구 사항
  - 모든 동물의 `ANIMAL_ID`, `NAME`, `DATETIME` 조회
  - 정렬 기준:
    1. `NAME` 오름차순 (사전순)
    2. 이름이 같을 경우 `DATETIME` 내림차순 (나중에 들어온 동물 우선)

## 정답 SQL

```sql
-- 이름 오름차순, 같은 이름 내에서는 보호 시작일 최신순으로 조회
SELECT
    ANIMAL_ID,
    NAME,
    DATETIME
FROM ANIMAL_INS
ORDER BY NAME ASC, DATETIME DESC;
```
