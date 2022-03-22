# Palindrome Number
`x` 라는 숫자 타입의 파라미터가 들어온다. 파라미터 `x` 가 [palindrome](https://ko.wikipedia.org/wiki/%ED%9A%8C%EB%AC%B8) 한 숫자인지 확인하는 함수를 만들어라.

### Code
  ```javascript
  /**
  * @param {number} x
  * @return {boolean}
  */
  var isPalindrome = function(x) {
      const numArray = String(x).split('');

      while (numArray.length > 1) {
          if (numArray.shift() !== numArray.pop()) {
              return false;
          }
      }

      return true;
  };
  ```

### 풀이
  - `x` 의 모든 요소를 빠르게 탐색하기 위해, 배열의 형태로 만들었다.
  - `x` 의 값이 거꾸로 뒤집어도 같은 값인지 확인하기 위해서는 queue 형태와 stack 형태의 데이터 구조를 합치면 되지 않을까 생각했다.
  - 데이터 구조를 두개를 가져다 쓰고, 같은 값을 다시 탐색하는 일이 없으므로, 반목의 더 적제 발생한다. 
  - `numArray.length` 도 계속 줄기 때문에 무한 반복 걱정이 없다. 

### 결과 
  ```
  Runtime: 246 ms, faster than 59.18% of JavaScript online submissions for Palindrome Number.
  Memory Usage: 50.9 MB, less than 58.96% of JavaScript online submissions for Palindrome Number.
  ```

### 노트
  - Javascript 로 푼 가장 vote 가 많은 풀이법을 보니, 놀랍게도 나랑 코드가 똑같았다. 아마 문제가 단순하고 쉬우니, 코드가 비슷할 수도 있겠다 싶었다.
  - while 문을 쓰는 건 어쩌면 유지보수 관점에선 불리할 수 있다.  
