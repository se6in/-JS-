# JS 코딩테스트 정리(프로그래머스) - 코딩테스트 입문

# [Day 1] 
# Day 2

나머지 구하기
```js
function solution(num1, num2) {
    var answer = 0;
    answer = num1 % num2; 
    return answer;
}
```
중앙값 구하기(sort,math)
```js
function solution(array) {
    const list = array.sort((a,b) => a-b)
    const center = Math.floor(array.length / 2)
    return list[center]
}
```
최빈값 구하기(틀림)(map,array)
```js
function solution(array) {
    let counting = new Map();
    let countArray = new Array;
    let max = 0;
    for(let i of array) {
        if(!counting.has(i)) counting.set(i, 0);
        if(counting.has(i)) counting.set(i, counting.get(i)+1);
        while(counting.get(i) > max) max++;
    }

    for (let [k, v] of counting) {
        if(v === max) countArray.push(k)
    }
    
    return countArray.length === 1 ? countArray[0] : -1;
}
```
짝수는 싫어요(array)
```js
function solution(n) {
    var answer = [];
    for(let i= 1; i <= n ; i++){
        if(i%2 === 1){
            answer.push(i);
        }
    }
    return answer;
}
```
피자 나눠 먹기 (1)
```js
function solution(n) {
    let pizza = 1;
    while (pizza * 6 % n) {
        pizza++;
    }
    return pizza;
}
```
피자 나눠 먹기 (2)
```js
const solution = (n) => {
    let piece = 6

    while(true) {
        if (piece % n === 0) {
            break
        }
        piece += 6
    }
    return piece / 6
}
```
피자 나눠 먹기 (3)
```js
function solution(slice, n) {
   var pizza = (n%slice == 0) ? n/slice : n/slice+1;
   return parseInt(pizza);
}
```
배열의 평균값
```js
function solution(numbers) {
    var sum = 0;
    for(let i=0; i<numbers.length;i++){
        sum += numbers[i];
    }
    let avg = sum / numbers.length
    return avg;
}
```
