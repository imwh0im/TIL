# Mongoose 에서 ObjectId 를 string 으로 전환하기

- Mongoose 로 쿼리해서 받아온 후 string 으로 쓰기
  ```typescript
  const query = { status: 'set', type: 'premium' };
  const result = await this.userModel.findOne(query);
  return result._id.toString(); // string return
  ```
