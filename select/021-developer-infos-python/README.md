# Python 개발자 찾기

## 문제 요약

- 테이블
  - **DEVELOPER_INFOS**: `ID`, `FIRST_NAME`, `LAST_NAME`, `EMAIL`, `SKILL_1`, `SKILL_2`, `SKILL_3`
- 요구 사항
  - Python 스킬을 가진 개발자 조회 (`SKILL_1`, `SKILL_2`, `SKILL_3` 중 하나라도 `'Python'`)
  - 조회 컬럼: `ID`, `EMAIL`, `FIRST_NAME`, `LAST_NAME`
  - 정렬: `ID` 오름차순

## 정답 SQL

```sql
-- Python 스킬을 가진 개발자 정보 조회
SELECT
    ID,
    EMAIL,
    FIRST_NAME,
    LAST_NAME
FROM DEVELOPER_INFOS
WHERE 'Python' IN (SKILL_1, SKILL_2, SKILL_3)
ORDER BY ID ASC;
```
