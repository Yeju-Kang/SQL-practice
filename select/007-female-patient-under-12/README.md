# 12세 이하인 여자 환자 목록 출력하기

## 문제 요약

- 테이블
  - **PATIENT**: `PT_NO`, `PT_NAME`, `GEND_CD`, `AGE`, `TLNO`
- 요구 사항
  - 조건: 성별 코드가 `'W'` 이고, 나이(`AGE`) ≤ 12
  - 조회 컬럼: `PT_NAME`, `PT_NO`, `GEND_CD`, `AGE`, `TLNO`
  - 전화번호(`TLNO`)가 없는 경우 `'NONE'` 으로 출력
  - 정렬:
    1. 나이(`AGE`) 내림차순
    2. 나이가 같다면 환자 이름(`PT_NAME`) 오름차순

## 정답 SQL

```sql
-- 12세 이하 여자 환자 목록 조회
SELECT
    PT_NAME,
    PT_NO,
    GEND_CD,
    AGE,
    IFNULL(TLNO, 'NONE') AS TLNO
FROM PATIENT
WHERE GEND_CD = 'W'
  AND AGE <= 12
ORDER BY AGE DESC, PT_NAME ASC;
```
