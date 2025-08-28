# 상위 N개 레코드

## 문제 요약

- 테이블
  - **ANIMAL_INS**: `ANIMAL_ID`, `ANIMAL_TYPE`, `DATETIME`, `INTAKE_CONDITION`, `NAME`, `SEX_UPON_INTAKE`
- 요구 사항
  - 보호소에 가장 먼저 들어온 동물의 `NAME` 조회
  - 정렬 기준: `DATETIME` 오름차순 → 가장 빠른 시간의 레코드 선택
  - 결과는 **한 마리**만 출력됨

## 정답 SQL

```sql
-- 보호소에 가장 먼저 들어온 동물의 이름 조회
SELECT
    NAME
FROM ANIMAL_INS
ORDER BY DATETIME ASC
LIMIT 1;
```
