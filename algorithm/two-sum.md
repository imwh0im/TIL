# TwoSum
`nums` 라는 정수의 배열과 `target` 이라는 정수가 파라미터로 들어온다. 정수 target 을 만들기 위해 nums 의 어떤 인덱스의 정수들을 더해야하는 지 구하는 문제 

### Code
```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {
    const numsLength = nums.length;
    for (let i = 0; i <= numsLength; i++) {
        const targetNum = nums.shift();
        const answerNum = target - targetNum;
        const answerNumIndex = nums.findIndex((num) => num === answerNum) + i + 1;

        if (answerNumIndex > i) {
            return [i, answerNumIndex];
        }
    }
};
```

### 풀이
  - `nums` 의 모든 요소를 탐색해야하기 때문에 순환을 요구한다. 
  - index 를 0 부터 늘리기 때문에 Stack 구조가 알맞다.
  - `array.shift()` 로 인해 배열의 크기가 줄어들기 때문에 햔재 인덱스인 i 와 1 을 더해줘야 원래의 (nums) 배열에서 정확한 index 를 구할 수 있다. 
    - `shift()` 를 사용한 이유는 `findIndex` 로 배열을 탐색하기 때문에, 배열을 크기를 줄일 수 있다면 유리하다고 판단했다.
  - `findIndex` 는 조건에 맞는 요소가 없을 경우 -1 을 반환하기 때문에, 요소가 없을 경우 `answerNumIndex` 의 값은 현재 인덱스인 i 와 같다. 
