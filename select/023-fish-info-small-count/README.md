# 잔챙이 잡은 수 구하기

## 문제 요약

- 테이블
  - **FISH_INFO**: `ID`, `FISH_TYPE`, `LENGTH`, `TIME`
- 요구 사항
  - **길이가 10cm 이하인 물고기 수** 조회
  - 단, `LENGTH`가 `NULL`로 기록된 경우가 곧 10cm 이하를 의미
  - 출력 컬럼명은 `FISH_COUNT`

## 정답 SQL

```sql
-- 길이가 10cm 이하(= LENGTH IS NULL)인 물고기의 수 조회
SELECT
    COUNT(*) AS FISH_COUNT
FROM FISH_INFO
WHERE LENGTH IS NULL;
```
