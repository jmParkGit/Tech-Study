# async/await란?
- React에서 async(비동기)란 순서대로 함수가 실행되게 하는 것
- Example
```jsx
const func = async function(){
	await func01()
  await func02()
}
```

```jsx
const func = async () => {
   await func01()
   await func02()
}
```

```jsx
async function func(){
	 await func01()
	 await func02()
}
```

```jsx
const func = async function(){
	await func01()
  await func02()
}
```

