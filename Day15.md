# 치킨 쿠폰
```js
function solution(chicken) {
    var answer = parseInt((chicken-1) / 9);
    return answer;
}
```
# 이진수 더하기
```js
function solution(bin1, bin2) {
    return (parseInt(bin1, 2) + parseInt(bin2, 2)).toString(2);
}
```
# A로 B 만들기
```js
function solution(before, after) {
    return before.split('').sort().join('') === after.split('').sort().join('') ? 1 : 0;
}
```
# k의 개수
```js
function solution(i, j, k) {
    let a ='';
    for(i;i<=j;i++){
        a += i;
    }

    return a.split(k).length-1;
}
```
