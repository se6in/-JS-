# 특이한 정렬
```js
function solution(numlist, n) {
  return numlist.sort((a, b) => Math.abs(a - n) - Math.abs(b - n) || b - a);
}
```
# 등수 매기기
```js
function solution(score) {
    let avg = score.map(v=>(v[0]+v[1])/2);
    let sorted = avg.slice().sort((a,b)=>b-a);
    return avg.map(v=>sorted.indexOf(v)+1);
}
```
# 옹알이 (1)
```js
function solution(babbling) {
  return babbling.map(word => word.replaceAll(/aya|ye|woo|ma/gi, '')).filter(a => a ==='').length
}
```
# 로그인 성공?
```js
function solution(id_pw, db) {
    for(let db_id_pw of db){
        if(db_id_pw[0]===id_pw[0]){
            if(db_id_pw[1]===id_pw[1]){
                return 'login'
            }else{
                return 'wrong pw'
            }
        }
    }
    return 'fail';
}
```
