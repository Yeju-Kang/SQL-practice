# 흉부외과 또는 일반외과 의사 목록 출력하기

## 문제 요약

- 테이블

  - **DOCTOR**: `DR_NAME`, `DR_ID`, `LCNS_NO`, `HIRE_YMD`, `MCDP_CD`, `TLNO`

- 요구 사항

  - 진료과(`MCDP_CD`)가 **흉부외과(CS)** 또는 **일반외과(GS)** 인 의사의 정보를 조회
  - 조회 컬럼: 의사 이름(`DR_NAME`), 의사 ID(`DR_ID`), 진료과 코드(`MCDP_CD`), 고용일자(`HIRE_YMD`)
  - 정렬: `HIRE_YMD`(DESC) → 동률 시 `DR_NAME`(ASC)
  - 날짜 포맷: `YYYY-MM-DD`

## 정답 SQL

```sql
SELECT
    DR_NAME,
    DR_ID,
    MCDP_CD,
    DATE_FORMAT(HIRE_YMD, '%Y-%m-%d') AS HIRE_YMD
FROM DOCTOR
WHERE MCDP_CD IN ('CS', 'GS')
ORDER BY HIRE_YMD DESC, DR_NAME ASC;
```
