# 3월에 태어난 여성 회원 목록 출력하기

## 문제 요약

- 테이블
  - **MEMBER_PROFILE**: `MEMBER_ID`, `MEMBER_NAME`, `TLNO`, `GENDER`, `DATE_OF_BIRTH`
- 요구 사항
  - 조건:
    - 성별 `GENDER = 'W'`
    - 생일이 **3월** → `MONTH(DATE_OF_BIRTH) = 3`
    - 전화번호 `TLNO` **NULL 제외**
  - 조회 컬럼: `MEMBER_ID`, `MEMBER_NAME`, `GENDER`, `DATE_OF_BIRTH`
  - 정렬: `MEMBER_ID` 오름차순
  - 날짜 포맷: `YYYY-MM-DD`

## 정답 SQL

```sql
-- 3월생 여성 회원(전화번호 있는 경우만) 조회
SELECT
    MEMBER_ID,
    MEMBER_NAME,
    GENDER,
    DATE_FORMAT(DATE_OF_BIRTH, '%Y-%m-%d') AS DATE_OF_BIRTH
FROM MEMBER_PROFILE
WHERE TLNO IS NOT NULL
  AND MONTH(DATE_OF_BIRTH) = 3
  AND GENDER = 'W'
ORDER BY MEMBER_ID ASC;
```
