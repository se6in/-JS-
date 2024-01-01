# 문자열 밀기
```js
function solution(A, B) {
    let arr = [...A]
    for(let i = 0; i< arr.length; i++){
        if(A === B)
            return i;
        else{
            arr.unshift(arr.pop())
            if(arr.join('') === B)
                return i+1;
        }
    }
    return -1;
}
```
# 종이 자르기
```js
function solution(M, N) {
  return M * N - 1;
}
```
# 연속된 수의 합
```js
function solution(num, total) {
    // 초기 값을 구하는 과정
    // total / num 으로 연속 되는 숫자의 중간 값을 구한다
    // 구한 중간값에서 num / 2의 내림을 해서 구한 자릿수 값을 빼고
    // 그 값을 올림으로 해서 초기 값을 구한다
    
    // ex) num = 3 / total = 12
    // total / num = 4
    // num / 2 = 1.5 >>> 1 (내림) Math.floor
    // 4 - 1 = 3 해서 초기값은 3(소수점이면 올려준다) Math.ceil
    const min = Math.ceil(total/num - Math.floor(num / 2));
    
    // Array.from() 매서드를 이용해 구해둔 초기값 부터 num의 길이 만큼 해서 답을 구한다.
    return Array.from({ length: num }, (_, i) => i + min);
}
```
# 다음에 올 숫자
```js
function solution(common) {
    const sameMinus = common[1]-common[0] === common[2]-common[1]
    if(sameMinus) {
        return common[common.length-1]+common[1]-common[0]
    } else {
        return common[common.length-1]*(common[1]/common[0])
    }
}
```
