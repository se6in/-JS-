# 점의 위치 구하기
```js
function solution(dot) {
    var answer = 0;
    if(dot[0] >= 0 && dot[1] >= 0){
        answer =1;
    }
    else if(dot[0] >=0 && dot[1] <=0){
        answer = 4;
    }
    else if(dot[0] <= 0 && dot[1] >=0){
        answer = 2;
    }
    else if(dot[0] <= 0 && dot[1] <= 0){
        answer = 3;
    }
    return answer;
}
```
# 2차원으로 만들기
```js
function solution(num_list, n) {
    const answer = [];

    while(num_list.length) {
        answer.push(num_list.splice(0, n));
    }
    return answer;
}
```
splice 내장함수는 첫번째 인자로 자르기 시작할 index로 주고, 두번째 인자로는 어디까지 자를 건지 하는 index를 넣어준다.

# 공 던지기
```js
function solution(numbers, k) {
    return numbers[(k - 1) * 2 % numbers.length];
}
```
# 배열 회전시키기
```js
function solution(numbers, direction) {
    if(direction === 'right') {
        numbers.unshift(numbers.pop())
    } else {
        numbers.push(numbers.shift())
    }
    return numbers
}
```
배열에 값을 추가하는 함수

.push() : 배열의 맨 끝에 값을 추가한다.

.unshift() : 배열의 맨 앞에 값을 추가한다.

배열에 값을 제거하는 함수

.pop() : 배열의 맨 끝에 값을 제거한다.

.shift() : 배열의 맨 앞에 값을 제거한다.
# 주사위의 개수
```js
function solution(box, n) {
  const x= Math.floor( box[0]/n)
  const y= Math.floor( box[1]/n)
  const z= Math.floor( box[2]/n)
  return  x*y*z
}
```
# 합성수 찾기
```js
function solution(n) {
    let answer = 0
    for(let i=1; i<=n; i++) {
        let counter = 0
        for(let j=1; j<=i ; j++) {
            if(i%j == 0) {
                counter += 1
            }
        }
        if(counter > 2) {
            answer += 1
        }
    }
    return answer
}
```
# 최댓값 만들기 (1)
```js
function solution(numbers) {
    numbers.sort((a,b)=>b-a); //내림차순
    return numbers[0]*numbers[1];
}
```
# 팩토리얼
```js
function solution(n) {
    var answer = 0;
    var fac = 1;
    for(let i =1 ; i <=n ; i++){
        fac *= i;
        if(fac === n){
            return i;
        }
        if(fac > n){
            return i-1;
        }
    }
}
```
