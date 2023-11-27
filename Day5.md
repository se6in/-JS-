# 배열 자르기
```js
function solution(numbers, num1, num2) {
    var answer = [];
    answer = numbers.slice(num1, num2+1);
    return answer;
}
```
# 외계행성의 나이
```js
function solution(age) {
    let alpha = ['a','b','c','d','e','f','g','h','i','j'];
    let answer = '';
    age = age.toString();
    
    for (let i = 0; i < age.length; i++) {
        answer += alpha[age[i]];
    }
    return answer;
}
```
# 진료 순서 정하기
```js
function solution(emergency) {
     let sorted = emergency.slice().sort((a,b)=>b-a);
    return emergency.map(v=>sorted.indexOf(v)+1);
}
```

sort((a,b)=> b-a)  는 내림차순해주는 함수

sorted.indexOf(v)는 sorted 배열에서 v의 인덱스를 찾아서 반환. 그리고 +1을 해주면 v가 sorted 배열에서 몇 번째로 큰 요소인지를 나타내는 순위를 구함

# 순서쌍의 개수
```js
function solution(n) {
    var answer = 0;
    for(let i = 2; i <= n; i++) {
    if(n % i === 0) answer++;
    }
    return answer + 1;
}
```
# 개미 군단
```js
function solution(hp) {
    let general = Math.floor(hp / 5) 
    let soldier = Math.floor((hp - general * 5) / 3) 
    let worker = hp - (general * 5) - (soldier * 3)
    return (general + soldier + worker)
}
```
# 모스부호 (1)
```js
function solution(letter) {
    var answer = '';
    var morse = { 
    '.-':'a','-...':'b','-.-.':'c','-..':'d','.':'e','..-.':'f',
    '--.':'g','....':'h','..':'i','.---':'j','-.-':'k','.-..':'l',
    '--':'m','-.':'n','---':'o','.--.':'p','--.-':'q','.-.':'r',
    '...':'s','-':'t','..-':'u','...-':'v','.--':'w','-..-':'x',
    '-.--':'y','--..':'z'
    }
  letter.split(" ").map(v => answer += morse[v]);
  return answer;
}
```
# 가위 바위 보
```js
function solution(rsp) {
    let result = '';
    for (let i = 0; i < rsp.length; i++) {
        if (rsp[i] === '2') {
            result += '0' 
        } else if (rsp[i] === '0') {
            result += '5'
        } else if (rsp[i] === '5') {
            result += '2'
        }
    } return result;
}
```

# 구슬을 나누는 경우의 수
```js
// 서로 다른 n개 중 m개를 뽑는 경우의 수 공식
function solution(balls, share) {
    return factorial(balls) / (factorial((balls-share)) * factorial(share))
}
// 팩토리얼을 구하는 함수
function factorial(num) {
    let returnFactorial = BigInt(1)
    for(let i = num; i >= 2; i-- ) {
        returnFactorial*=BigInt(i)
    }
    return returnFactorial
}
```
BigInt : 아주 큰 정수 숫자 표현을 위해 자바스크립트에서 새롭게 제공되는 프리미티브 숫자 타입
