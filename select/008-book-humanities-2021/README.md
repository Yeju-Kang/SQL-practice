# 2021년에 출판된 인문 카테고리 도서 조회하기

## 문제 요약

- 테이블
  - **BOOK**: `BOOK_ID`, `CATEGORY`, `AUTHOR_ID`, `PRICE`, `PUBLISHED_DATE`
- 요구 사항
  - 조건:
    - `CATEGORY = '인문'`
    - 출판일(`PUBLISHED_DATE`)이 **2021년**인 도서
  - 조회 컬럼: `BOOK_ID`, `PUBLISHED_DATE`
  - 정렬: 출판일(`PUBLISHED_DATE`) **오름차순**
  - 날짜 포맷: `YYYY-MM-DD`

## 정답 SQL

```sql
-- 2021년에 출판된 인문 카테고리 도서 조회
SELECT
    BOOK_ID,
    DATE_FORMAT(PUBLISHED_DATE, '%Y-%m-%d') AS PUBLISHED_DATE
FROM BOOK
WHERE YEAR(PUBLISHED_DATE) = 2021
  AND CATEGORY = '인문'
ORDER BY PUBLISHED_DATE ASC;
```
