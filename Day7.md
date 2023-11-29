# 모음 제거
```js
function solution(my_string) {
    return my_string.replace(/['a','e','i','o','u']/g,'')
}
```
/g는 모든 전역에 ['a','e','i','o','u']를 찾는다. 두번째 ''파라미터는 공백으로 바꾼다.
# 문자열 정렬하기 (1)
```js
function solution(my_string) {
    return my_string.match(/\d/g).sort((a, b) => a - b).map(n => Number(n));
}
```
\d는 0~9의미

match() 메소드는 정규식 조건에 맞는 것들을 배열로 만들어준다.

map() 메소드는 기존 배열을 수정하지 않고 새로운 배열을 만들어낸다 .
# 숨어있는 숫자의 덧셈 (1)
```js
function solution(my_string) {
    const answer = my_string
                        .replace(/[^0-9]/g,'')
                        .split('')
                        .map(v=>Number(v))
                        .reduce((acc,cur)=>acc+cur)
    return answer 
}
```
/[^0-9]/g : '숫자0~9'가 아닌 것을 모두 찾는다. `` 공백으로 만든다.

accumulator : 콜백 함수의 반환 값 또는 이전 순회에서의 최종 결과값. 

초기 값(initialValue)이 제공된 경우 첫 번째 순회에서는  initialValue로 설정된다.

current : 현재 돌고 있는 요소

# 소인수분해
```js
function solution(n) {
    let answer = [];
    let i = 2;
    while (n != 1) {
        if (n % i == 0) {
            answer.push(i)
            while (n % i == 0) {
                n = n / i; 
            }
        }
        i++;
    }
    return answer;
}
```
# 컨트롤 제트
```js
function solution(s) {
    s = s.split(" ")
    while(s.includes('Z')) {
        s.splice(s.indexOf('Z')-1,2)
    }
    return s.reduce((a,b) => a+Number(b), 0)
}
```
# 배열 원소의 길이
```js
function solution(strlist) {
    return strlist.map((el) => el.length)
}
```
el : elmental(원소)

el.lenght : 원소의 길이
# 중복된 문자 제거
```js
function solution(my_string) {
    var answer = new Set([...my_string])
    return [...answer].join('');
}
```
... : 전개 연산자는 배열 또는 객체를 하나하나 넘기는 용도로 사용된다.

Set 특성이 중복 X
# 삼각형의 완성조건 (1)
```js
function solution(sides) {
    sides = sides.sort((a,b) => a-b)
    return sides[0]+sides[1] > sides[2] ? 1 : 2;
}
```
