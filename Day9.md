# 편지
```js
function solution(message) {
    return message.length*2;
}
```
# 가장 큰 수 찾기
```js
function solution(array) {
    let a = Math.max(...array);
    return [a, array.indexOf(a)]
}
```
# 문자열 계산하기
```js
function solution(my_string) {
    const splited = my_string.split(" ");
    
    let answer = Number(splited[0]);
    
    splited.forEach((item, index) => {
        if(item === "+"){
            answer += Number(splited[index + 1]);
        }
        
        if(item === "-"){
            answer -= Number(splited[index + 1]);
        }
    })
    
    return answer;
}
```
# 배열의 유사도
```js
function solution(s1, s2) {
    var answer = 0;
    for (let i = 0; i < s1.length; i++){
        for (let j = 0; j < s2.length; j++){
            if(s1[i] === s2[j]) answer++;
        }
    }
    return answer;
}
```
# 숫자 찾기
```js
function solution(num, k) {
    return num.toString().split("").map((el) => Number(el)).indexOf(k) + 1 || -1
}
```
# n의 배수 고르기
```js
function solution(n, numlist) {
    return numlist.filter(num => num % n === 0);
}
```
# 자릿수 더하기
```js
function solution(n){
    let answer = 0;
    let a = String(n);
    for(i=0; i<a.length; i++) {
      answer += parseInt(a[i]);
    }
    return answer;
}
```
# OX퀴즈
```js
function solution(quiz) {
  let answer = [];
  quiz.forEach((val) => {
    const [x, sign, y, , z] = val.split(" ");
    let sum = 0;
    if (sign === "+") sum = Number(x) + Number(y);
    else sum = Number(x) - Number(y);
    sum === Number(z) ? answer.push("O") : answer.push("X");
  });
  return answer;
}
```
자바스크립트의 forEach() 함수는 배열을 순회해서 처리하는 데 사용되는 메서드

map()메서드와 거의 비슷하지만 차이점은 따로 return 하는 값이 없다.
