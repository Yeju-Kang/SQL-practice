# 조건에 맞는 개발자 찾기

## 문제 요약

- 테이블
  - **SKILLCODES**: `NAME`, `CATEGORY`, `CODE`
  - **DEVELOPERS**: `ID`, `FIRST_NAME`, `LAST_NAME`, `EMAIL`, `SKILL_CODE`
- 요구 사항
  - Python 또는 C# 스킬을 가진 개발자 조회
  - 출력 컬럼: `ID`, `EMAIL`, `FIRST_NAME`, `LAST_NAME`
  - 정렬: `ID` 오름차순

## 핵심 로직

- `SKILL_CODE` 는 여러 스킬의 **비트 합**으로 표현됨.
- 특정 스킬 보유 여부는 **비트 AND 연산자(&)** 로 확인 가능.
  - Python: `CODE = 256`
  - C#: `CODE = 1024`
- 따라서 `SKILL_CODE & 256 != 0` 또는 `SKILL_CODE & 1024 != 0` 인 경우가 조건에 해당됨.

## 정답 SQL

```sql
-- Python(256) 또는 C#(1024) 스킬을 가진 개발자 조회
SELECT
    ID,
    EMAIL,
    FIRST_NAME,
    LAST_NAME
FROM DEVELOPERS
WHERE (SKILL_CODE & 256) != 0
   OR (SKILL_CODE & 1024) != 0
ORDER BY ID ASC;
```
