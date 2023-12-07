# 직사각형 넓이 구하기
```js
function solution(dots) {
    dots.sort((a,b) => a[0] - b[0]);
    
    const height = Math.abs(dots[0][1] - dots[1][1]);
    const width = Math.abs(dots[0][0] - dots[2][0]);
    
    return height * width;
}
```
Math.abs : 절대값
# 캐릭터의 좌표(틀림)
```js
function solution(keyinput, board) {
    let x = 0;
    let y = 0;
    
    let xRange = (board[0] / 2);
    let yRange = (board[1] / 2);
    
    for (let i = 0; i < keyinput.length; i ++ ) {

        if (keyinput[i] === "right" && x + 1 < xRange) x++ 
        if (keyinput[i] === "left" && x - 1 > -xRange) x-- 
        
        if (keyinput[i] === "up" && y + 1 < yRange) y++
        if (keyinput[i] === "down" && y - 1 > -yRange) y--
    }
    return [x, y]
    
}
```
# 최댓값 만들기 (2)
```js
function solution(numbers) {
    numbers.sort((a, b) => a - b);
    return Math.max(numbers[0] * numbers[1], numbers[numbers.length-1] * numbers[numbers.length-2]);
}
```
Math.max : 인자중에 큰값을 리턴

# 다항식 더하기(틀림)
```js
function solution(polynomial) {
  const splited = polynomial.split(" + ");
  // 공백과 '+'연산 기호 제거하고 값들만 남은 배열

  let xArr = splited
    .filter((v) => v.includes("x"))
    .map((v) => (v.split("x")[0] ? v.split("x")[0] : 1));
	// 'x'포함된 배열 중, 'x'로 split했을 때 숫자가 나온 것들은 숫자만 반환,
	// 나머지는 빈 값이므로 1로 반환된 배열로 만들어 줌 (ex: '3x'면 '3', 'x'면 1로 반환)

  let constArr = splited.filter((v) => !v.includes("x"));
  // 'x'를 포함하지 않은 상수 배열

  if (xArr.length && constArr.length) {
  // x항과 상수항 둘 다 값이 1개 이상 있는 경우
    xArr = xArr.reduce((a, b) => +a + +b);
    constArr = constArr.reduce((a, b) => +a + +b);
    return xArr == 1 ? `x + ${constArr}` : `${xArr}x + ${constArr}`;
	// x항의 합이 1인 경우 1x가 아닌 x를 리턴해야 하므로 조건문 추가

  } else {
    if (xArr.length) {
	// x항만 값이 있는 경우
      xArr = xArr.reduce((a, b) => +a + +b);
      return xArr == 1 ? "x" : `${xArr}x`;
    }
    if (constArr.length) {
	// 상수항만 값이 있는 경우
      constArr = constArr.reduce((a, b) => +a + +b);
      return constArr + "";
    }
  }
}
```
