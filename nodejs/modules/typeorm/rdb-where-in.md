# RDB에서 where in Query 주의점
  - typeORM 을 통해서 `SELECT * FROM db.table WHERE column IN ()` 쿼리 할 떄 빈값인 경우
    - null 을 포함해서 `syntax error` 를 대비한다.
    ```typescript
    async function getUsers(userIds: string[]) {
      const queryResult = await this.userModel
        .createQueryBuilder()
        .select()
        .where('id IN (:userIds)', { userIds: [null, ...userIds] })
        .getOne();
      return queryResult;
    }
    ```
