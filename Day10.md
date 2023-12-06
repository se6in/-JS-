# 문자열안에 문자열
```js
function solution(str1, str2) {
    var answer = 0;

    if(str1.includes(str2)){
        answer = 1;
    }else{
        answer = 2;
    }

    return answer;
}
```
includes() 메서드는 문자열에 다른 문자열이 포함되어 있는지 여부를 확인(대소문자를 구분)
# 제곱수 판별하기
```js
function solution(n) {
    return Math.sqrt(n) % 1 === 0 ? 1 : 2;
}
```
Math.sqrt : 함수 인자로 값을 넘겨주면 루트 값을 반환한다.

만약 매개변수가 음수이면 NaN을 반환한다.
# 세균 증식
```js
function solution(n, t) {
  for ( let i = 1; i <= t; i++ ) {
    n *= 2
  }
    return n;
}
```
# 문자열 정렬하기 (2)
```js
function solution(my_string) {
    return my_string.toLowerCase().split('').sort().join('');
}
```
# 7의 개수
```js
function solution(array) {
    return array.join('').split('7').length - 1;
}
```
# 잘라서 배열로 저장하기
```js
function solution(my_str, n) {
    const answer = []
    for (let i=0; i*n < my_str.length; i++) {
        answer.push(my_str.substr(i*n, n))
    }
    
    return answer;
}
```
substr : 문자열에서 특정한 구간의 문자열을 추출한다.
# 중복된 숫자 개수
```js
function solution(array, n) {
    var answer = 0;
    for(var i = 0; i < array.length; i++){
        if(array[i] == n){
            answer++
        }
    }
    return answer;
}
```
# 머쓱이보다 키 큰 사람
```js
function solution(array, height) {
    var answer = 0;
    for(let i=0; i<array.length; i++){
        if(array[i]> height){
            answer++;
        }
    }
    return answer;
}
```
