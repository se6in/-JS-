# 옷가게 할인 받기
```js
function solution(price) {
    var answer = 0;

    // 50 만원 이상 20%
    if (price >= 500000) {
        answer = Math.floor(price - (price * 0.2));
    }
    // 30 만원 이상 10%
    else if (price >= 300000) {
        answer = Math.floor(price - (price * 0.1));
    }
    // 10 만원 이상 5%
    else if (price >= 100000) {
        answer = Math.floor(price - (price * 0.05));
    }
    else {
        answer = Math.floor(price);
    }

    return answer;
}
```
Math.floor() : 소수점 이하를 버림한다.

Math.ceil() : 소수점 이하를 올림한다.

Math.round() : 소수점 이하를 반올림한다.

# 아이스 아메리카노
```js
function solution(money) {
    var americano = 5500;
    var cup = Math.floor(money/americano);
    var changes = Math.floor(money - americano*cup);
    return [cup,changes];
}
```
# 나이 출력
```js
function solution(age) {
    let years = 2022 - age + 1;
    return age,years;
}
```
# 배열 뒤집기
```js
function solution(num_list) {
    var answer = [];
    answer = num_list.reverse();
    return answer;
}
```
Array.reverse() : 배열의 순서를 반대로 뒤집어주는 함수이다.

# 문자열 뒤집기
```js
function solution(my_string) {
    var answer = '';
    answer = my_string.split('').reverse().join('');
    return answer;
}
```
split() 메서드는 String 객체를 지정한 구분자를 이용하여 여러 개의 문자열로 나눕니다.

reverse() 메서드는 배열의 순서를 반전합니다. 첫 번째 요소는 마지막 요소가 되며 마지막 요소는 첫 번째 요소가 됩니다.

join() 메서드는 배열의 모든 요소를 연결해 하나의 문자열로 만듭니다.

