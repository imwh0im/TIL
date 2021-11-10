# provider 의 순환 종속성

- `/users/users.service.ts` 와 `/auth/auth.service.ts` 가 서로 종속성을 가지고 있을 때.
  ```typescript
  // /users/users.service.ts

  @Injectable()
  export class UsersService {
    constructor(private authService: AuthService) {}
  }
  ```

  ```typescript
  // /auth/auth.service.ts

  @Injectable()
  export class AuthService {
    constructor(private usersSerivce: UsersService) {}
  }
  ```
- 각 프로바이더가 서로의 종속성을 가진 경우에는 에러가 발생한다.
- 아래와 같은 처리를 하면 이를 해결할 수 있다.
  ```typescript
  // /users/users.service.ts

  @Injectable()
  export class UsersService {
    constructor(
      @Inject(forwardRef(() => AuthService)) // add
      private authService: AuthService
    ) {}
  }
  ```

  ```typescript
  // /auth/auth.service.ts

  @Injectable()
  export class AuthService {
    constructor(
      @Inject(forwardRef(() => UsersService)) // add
      private usersSerivce: UsersService
    ) {}
  }
  ```
