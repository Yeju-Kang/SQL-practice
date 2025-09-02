# 특정 형질을 가지는 대장균 찾기

## 문제 요약

- 테이블
  - **ECOLI_DATA**: `ID`, `PARENT_ID`, `SIZE_OF_COLONY`, `DIFFERENTIATION_DATE`, `GENOTYPE`
- 요구 사항
  - **2번 형질이 없음** → `GENOTYPE`의 **bit 2**가 꺼져 있음
  - **1번 또는 3번 형질 보유** → `GENOTYPE`의 **bit 1** 또는 **bit 3**이 켜져 있음
  - 출력: 조건을 만족하는 개체 수 `COUNT`

## 핵심 로직 (비트 연산)

- 형질 n 보유 여부: `GENOTYPE & (2^(n-1))`
  - 1번 형질 → `1`
  - 2번 형질 → `2`
  - 3번 형질 → `4`

## 정답 SQL

```sql
-- 2번 형질이 없고(= bit 2 꺼짐), 1번 또는 3번 형질이 있는 개체 수
SELECT
    COUNT(*) AS COUNT
FROM ECOLI_DATA
WHERE (GENOTYPE & 2) = 0          -- 2번 형질 없음
  AND (GENOTYPE & 1) != 0         -- 1번 형질 보유
    OR (GENOTYPE & 2) = 0 AND (GENOTYPE & 4) != 0;  -- 또는 3번 형질 보유
```
