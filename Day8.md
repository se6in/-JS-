# 가까운 수
```js
function solution(array, n) {
    array.sort((a,b) => Math.abs(n - a) - Math.abs(n - b) || a - b);

    return array[0];
}
```
abs : 절댓값 계산

|| (or): 둘중하나만 참이어도 참
# 369게임
```js
function solution(order) {
  return [...order.toString().matchAll(/[3|6|9]/g)].length;
}
```
# 암호 해독
```js
function solution(cipher, code) {
    let realcipher = "";
    for (let i = code-1; i < cipher.length; i += code) {
        realcipher += cipher[i];
    } return realcipher
}
```
# 대문자와 소문자
```js
function solution(my_string) {
    let arr = [];
    for (let i = 0; i < my_string.length; i++) {
        if (my_string[i] === my_string[i].toUpperCase()) {
            arr.push(my_string[i].toLowerCase())
        } else {
            arr.push(my_string[i].toUpperCase())
        }
    } return arr.join('')
}
```
toUpperCase : 대문자로 변환

toLowerCase : 소문자로 변환
# 영어가 싫어요
```js
function solution(numbers) {
    const num = ["zero", "one", "two", "three", "four", "five", "six", "seven", "eight", "nine"];
    
    for(let i = 0; i < num.length; i++){
        numbers = numbers.split(num[i]).join(i)
    }
    return Number(numbers)
}
```
# 인덱스 바꾸기
```js
function solution(my_string, num1, num2) {
  let arr = my_string.split("");
  [arr[num1], arr[num2]] = [arr[num2], arr[num1]];
  return arr.join("");
}
```
# 한 번만 등장한 문자
```js
function solution(s) {
    let res = [];
    for (let c of s) if (s.indexOf(c) === s.lastIndexOf(c)) res.push(c);
    return res.sort().join('');
}
```
lastIndexOf : 끝에서부터 검색할 값을 찾기 시작
# 약수 구하기
```js
function solution(n) {
    var answer = [];
    for(let i = 1; i<= n; i++){
        if (n%i == 0){
            answer.push(i);
        }
    }
    return answer
}

```
