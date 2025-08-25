# 서울에 위치한 식당 목록 출력하기

## 문제 요약

- 테이블
  - **REST_INFO**: `REST_ID`, `REST_NAME`, `FOOD_TYPE`, `VIEWS`, `FAVORITES`, `PARKING_LOT`, `ADDRESS`, `TEL`
  - **REST_REVIEW**: `REVIEW_ID`, `REST_ID`, `MEMBER_ID`, `REVIEW_SCORE`, `REVIEW_TEXT`, `REVIEW_DATE`
- 요구 사항
  - 서울에 위치한 식당(`ADDRESS`가 '서울'로 시작)만 대상
  - 조회 컬럼: `REST_ID`, `REST_NAME`, `FOOD_TYPE`, `FAVORITES`, `ADDRESS`, **리뷰 평균 점수(SCORE)**
  - 리뷰 평균 점수는 **소수점 둘째 자리까지**(소수 셋째 자리 반올림)
  - 정렬: `SCORE` 내림차순 → 동률 시 `FAVORITES` 내림차순

## 정답 SQL

```sql
-- 서울 소재 식당의 평균 리뷰 점수(소수 둘째 자리 반올림) 조회
SELECT
    i.REST_ID,
    i.REST_NAME,
    i.FOOD_TYPE,
    i.FAVORITES,
    i.ADDRESS,
    ROUND(AVG(r.REVIEW_SCORE), 2) AS SCORE
FROM REST_INFO AS i
JOIN REST_REVIEW AS r
  ON i.REST_ID = r.REST_ID
WHERE i.ADDRESS LIKE '서울%'
GROUP BY
    i.REST_ID, i.REST_NAME, i.FOOD_TYPE, i.FAVORITES, i.ADDRESS
ORDER BY
    SCORE DESC,
    i.FAVORITES DESC;
```
