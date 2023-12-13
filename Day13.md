# 저주의 숫자 3
```js
function solution(n) {
    var answer = 0;
    for(let i=1; i<=n; i++){
        if(i%3 == 0){
            n++;
        }
        if(String(i).includes("3")& i%3 != 0){
            n++
        }
    }
    return n;
}
```
# 평행
```js
function solution(dots) {
    if((dots[0][1] - dots[1][1]) / (dots[0][0] - dots[1][0]) === (dots[2][1] - dots[3][1]) / (dots[2][0] - dots[3][0])) return 1
    if((dots[0][1] - dots[2][1]) / (dots[0][0] - dots[2][0]) === (dots[1][1] - dots[3][1]) / (dots[1][0] - dots[3][0])) return 1
    if((dots[0][1] - dots[3][1]) / (dots[0][0] - dots[3][0]) === (dots[2][1] - dots[1][1]) / (dots[2][0] - dots[1][0])) return 1
    return 0
}
```
# 겹치는 선분의 길이(틀림)
```js
function solution(lines) {
    let line = new Array(200).fill(0);

    lines.forEach(([a, b]) => {
        for(; a < b; a++) line[a+100]++;
    });

    return line.reduce((a, c) =>  c > 1 ? a + 1 : a, 0)
}
```
# 유한소수 판별하기
```js
function solution(a, b) {

    let g = 1;
    for (let i = 1; i<= b; i++){
        if(a%i ===0 && b%i ===0) g = i;
    }
    
    b /= g    

    while (b%2 === 0) b = b/2
    while (b%5 === 0) b = b/5

    return b === 1? 1 : 2;
}
```
