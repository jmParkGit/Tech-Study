# var, let,const 비교
- var: 함수 단위
- let: block{} 단위(변수)
- const: block{} 단위(상수)
## 예제
```jsx
function scope(){
	const a = 0;
	let b = 0;
	var c = 0;
	
	if(a === 0){
		const a = 1;
		let b = 1;
		var c = 1;
		console.log(a, b, c); //1 1 1
	}
	
	console.log(a, b, c); //0 0 1
}
```
