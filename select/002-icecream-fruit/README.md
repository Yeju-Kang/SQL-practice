# 과일로 만든 아이스크림 고르기

## 문제 요약

- 테이블
  - **USED_GOODS_BOARD**: `BOARD_ID`, `WRITER_ID`, `TITLE`, `CONTENTS`, `PRICE`, `CREATED_DATE`, `STATUS`, `VIEWS`
  - **USED_GOODS_REPLY**: `REPLY_ID`, `BOARD_ID`, `WRITER_ID`, `CONTENTS`, `CREATED_DATE`
- 요구 사항
  - **2022-10**(10월)에 작성된 **댓글 기준**으로 다음 컬럼을 조회
    - 게시글 제목(`TITLE`), 게시글 ID(`BOARD_ID`), 댓글 ID(`REPLY_ID`), 댓글 작성자 ID(`WRITER_ID`), 댓글 내용(`CONTENTS`), 댓글 작성일(`CREATED_DATE`)
  - 정렬: `댓글 작성일`(ASC) → 동률 시 `게시글 제목`(ASC)
  - `CREATED_DATE` 포맷: `YYYY-MM-DD`

## 정답 SQL

```sql
SELECT
    b.TITLE,
    r.BOARD_ID,
    r.REPLY_ID,
    r.WRITER_ID,
    r.CONTENTS,
    DATE_FORMAT(r.CREATED_DATE, '%Y-%m-%d') AS CREATED_DATE
FROM USED_GOODS_BOARD AS b
JOIN USED_GOODS_REPLY AS r
    ON b.BOARD_ID = r.BOARD_ID
WHERE r.CREATED_DATE >= '2022-10-01'
  AND r.CREATED_DATE <  '2022-11-01'
ORDER BY r.CREATED_DATE ASC, b.TITLE ASC;
```
