# 직각삼각형 출력하기(틀림)
```js
const readline = require('readline');
    //모듈 가져오기//
const rl = readline.createInterface({
    // 인터페이스 객체 만들기//
    input: process.stdin,
    output: process.stdout
});

let input = [];

rl.on('line', function (line) {
     // 입력 받은 값을 처리하는 코드 //
    input = line.split(' ');
}).on('close', function () {
     // 입력이 끝나고 실행하는 코드 //
   const num = Number(input[0]);
   let logStr = ''
    for(let i = 0 ; i < num; i++) {
        for(let j = 0 ; j <= i; j++) {
            logStr+='*'
        }
        logStr+='\n'
    }
    console.log(logStr)
});
```
# 짝수 홀수 개수
```js
function solution(num_list) {
    var answer = [];
    var even = 0;
    var odd = 0;
    var len = num_list.length
    for(let i = 0 ; i < len ; i++){
        if (num_list[i] % 2 == 0){
             even ++;
    }
        else{
            odd ++;
        }
  }
    answer = [even,odd];
    return answer;
}
```
# 문자 반복 출력하기
```js
function solution(my_string, n) {
    var answer = '';
    for (let i = 0; i < my_string.length ; i++)
        for(let j = 0 ; j < n ; j++){
            answer += my_string[i];
        }
    return answer;
}
```
# 특정 문자 제거하기
```js
function solution(my_string, letter) {
    const answer = my_string.split(letter).join('')
    return answer;
}
```
# 각도기
```js
function solution(angle) {
    if(0< angle && angle < 90){
        return 1;
    }
    else if(angle === 90){
        return 2;
    }
    else if(90 < angle && angle < 180){
        return 3;
    }
    else if(angle === 180){
        return 4;
    }
}
```
&& 연산 활용하기
# 양꼬치
```js
function solution(n, k) {
    var price = 0;
    var yang = n * 12000;
    var drink = k * 2000;
    var service = Math.floor(n/10) * 2000;
    price = yang + drink - service;
    return price;
}
```
# 짝수의 합
```js
function solution(n) {
    var answer = 0;
    for(let i = 1 ; i <= n; i++){
        if(i % 2 === 0){
          answer += i;
      }
    }
    return answer;
}
```
