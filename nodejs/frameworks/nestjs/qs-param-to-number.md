# Query Param number 로 바꾸기

- Query param number 로 데이터 타입 바꾸기
- 아래 처럼하면 query param 을 number 로 타입을 바꿀 수 있다.
  ```typescript
  export class GetUsersQuery{
    @IsNumber()
    @Type(() => Number)
    country: number;

    @IsString()
    name: string;
  }
  ```
