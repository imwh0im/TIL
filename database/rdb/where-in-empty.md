# where in 에서 값이 없을 때

다음과 같은 쿼리는 에러가 납니다.
```sql
SELECT
  *
FROM
  db.table
where
  id IN ();
```

다음과 같은 쿼리로 쓸수 있습니다.
```sql
SELECT
  *
FROM
  db.table
WHERE
  id IN (null);
```
