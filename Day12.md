# 숨어있는 숫자의 덧셈 (2)
```js
function solution(my_string) {
    return my_string.split(/[a-zA-Z]/g).reduce((a,c)=>+a + +c, 0);
}
```
# 안전지대(틀림)
```js
function solution(board) {
  let answer = 0;
	
  // 위험지역 xy좌표(왼,오,위,아래,대각선4개방향)
  const dangerArea = [
		[-1, 0], [1, 0], [0, 1], [0, -1], [-1, 1], [1, 1], [1, -1], [-1, -1]
	]; 
	
  for (let i = 0; i < board.length; i++) {
    for (let j = 0; j < board[i].length; j++) {
      if (board[i][j] == 1) {
        dangerArea.map((v) => {
          let [x, y] = v;
          [x, y] = [x + i, y + j];
          if (
            x >= 0 &&
            x < board.length &&
            y >= 0 &&
            y < board[i].length &&
            board[x][y] == 0
          )
            board[x][y] = 2;
        });
      }
    }
  }
  board.map(v1 => v1.map(v2 => v2 == 0 ? answer++ : 0));
  return answer;
}
```
# 삼각형의 완성조건 (2)
```js
function solution(sides) {
    let count = 0
    const max = Math.max(...sides)
    const min = Math.min(...sides)

    for(let i = max-min+1 ; i <= max ; i ++) {
        count++
    }

    for(let i = max+1 ; i < max+min ; i ++) {
        count++
    }
    return count
}
```
# 외계어 사전
```js
function solution(spell, dic) {
return dic.some(s => spell.sort().toString() == [...s].sort().toString())
        ? 1 : 2
}
```
array.some : 배열순회시 조건에 맞으면 순회중단하고 true , 없으면 false
