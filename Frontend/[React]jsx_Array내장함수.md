# Array 내장 함수

## map
- 변환한 값으 새로운 배열로 만들어줌
```jsx
const array_num = [0, 1, 2, 3, 4, 5];

const new_array = array_num.map((array_item) =>{ 
	return array_item + 1;
});
// 새 배열의 값은 원본 배열 원소에 +1 한 값입니다.
console.log(new_array);
// 원본 배열은 그대로
console.log(array_num);
```

## filter
- 조건으 만족하는 항목만 골라서 새 배열을 만들어주느 함수
```jsx
const array_num = [0, 1, 2, 3, 4, 5];

// forEach(콜백함수)
const new_array = array_num.filter((array_item) => {
	// 특정 조건을 만족할 때만 return 하면 됨.
	// return에는 true 혹은 false가 들어가야 함.
	return array_item > 3;
});

console.log(new_array);
```

## concat
- 배열과 배열을 합치거나 배열에 특정값을 추가해주는 함수
```jsx
const array_num01 = [0, 1, 2, 3];
const array_num02 = [3, 4, 5];

const merge = array_num01.concat(array_num02);

console.log(merge); //[0, 1, 2, 3, 3, 4, 5]
```

## from
- 배열을 만들고자 하는 것이나, 유사배열으 복사해서 새로운 배열을 만들 때 사용
- 새로운 배열을 만들때(초기화 할때) 사용
- 유사배열은 배열으 내장함수를 사용 못하느 배열. 예로들어 DOM nodelist
```jsx
// 배열화
const my_name = "mean0";
const my_name_array = Array.from(my_name);
console.log(my_name_array);//['m', 'e', 'a', 'n', '0']

// 길이가 문자열과 같고, 0부터 4까지 숫자를 요소로 갖는 배열 만들기
const text_array = Array.from('hello', (item, idx) => {return idx});

console.log(text_array);//[0, 1, 2, 3, 4]


// 새 배열을 만들기(=> 빈 배열을 초기화)
// 길이가 4고, 0부터 3까지 숫자를 요소로 갖는 배열을 만들기
const new_array = Array.from({length: 4}, (item, idx)=>{ return idx;});

console.log(new_array);// [0, 1, 2, 3]
```
