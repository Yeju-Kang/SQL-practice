# 가장 큰 물고기 10마리 구하기

## 문제 요약

- 테이블
  - **FISH_INFO**: `ID`, `FISH_TYPE`, `LENGTH`, `TIME`
- 조건
  - `LENGTH`가 `NULL`인 경우 = **10cm 이하 물고기**, 제외
  - 가장 큰 물고기 **10마리**만 조회
- 출력 컬럼: `ID`, `LENGTH`
- 정렬 기준:
  1. `LENGTH` 내림차순
  2. 길이가 같으면 `ID` 오름차순

## 정답 SQL

```sql
-- 가장 큰 물고기 10마리의 ID와 길이 조회
SELECT
    ID,
    LENGTH
FROM FISH_INFO
WHERE LENGTH IS NOT NULL
ORDER BY LENGTH DESC, ID ASC
LIMIT 10;
```
