# DTO 내에서 기본값 지정

- 아래와 같이 하면 `~.dto.ts` 를 이용하여 기본 값을 지정해줄 수 있다.
  ```typescript
  class queries {
    @IsNumber()
    public id!: number;

    @IsString()
    @IsOptional()
    public name = 'Anonymous';

    @IsString()
    @IsOptional()
    public requestTime = dayjs().format('YYYY-MM-DD HH:mm:ss');
  }

  export default class CatsController {
    constructor(private catsService: CatsService) {}

    createUser(@Query() query: queries) {
      // query 의 name 이나 requestTime 이 없어도 queries Class 에서 지정한 기본값이 적용됨. 
      return this.catsService.insertUser(query);  
    }
  }
  ```
