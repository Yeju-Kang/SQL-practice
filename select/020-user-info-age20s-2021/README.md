# 조건에 맞는 회원수 구하기

## 문제 요약

- 테이블
  - **USER_INFO**: `USER_ID`, `GENDER`, `AGE`, `JOINED`
- 요구 사항
  - 조건:
    - 가입일(`JOINED`)이 **2021년**
    - 나이(`AGE`)가 **20세 이상 29세 이하**
  - 조회 컬럼: 조건에 맞는 회원 수(`USERS`)

## 정답 SQL

```sql
-- 2021년에 가입한 20~29세 회원 수 조회
SELECT
    COUNT(*) AS USERS
FROM USER_INFO
WHERE YEAR(JOINED) = 2021
  AND AGE BETWEEN 20 AND 29;
```
