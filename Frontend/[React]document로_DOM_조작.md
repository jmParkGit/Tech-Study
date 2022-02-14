# document로_DOM_조작
## document로_DOM에_접근하기
1.
```jsx
const wraps = document.getElementsByClassName("wrap");
console.log(wraps);
```

2.
```jsx
const title = document.getElementById("title");
title.style.backgroundColor = "yellow";
```

3.
```jsx
function sayHello (event) {
            console.log("hello");             
         }

const buttons = document.getElementsByTagName("button");

for (let i=0; i< buttons.length; i++){
  // .addEventListener()로 클릭 이벤트를 연결해줍니다. 
  buttons[i].addEventListener("click", sayHello);
}
```

## document에 DOM elements 추가하기
```jsx
const new_div = document.createElement("div");

new_div.style.backgroundColor = "green";
new_div.style.width = "100px";
new_div.style.height = "100px";

// 요소를 body에 추가해줍시다.
document.body.appendChild(new_div);
```

