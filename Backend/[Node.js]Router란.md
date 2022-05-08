# Router란?
- Routing은 Client의 요청에 대응해 응답하는 방식
- Router는 Middleware 기반으로 구현된 객체이므로 Middleware와 동일한 방식으로 작동함

## Node.js로 Router 사용해보기
```jsx
//app.js
const express = require("express");
const goodsRouter = require("./routes/goods.js");

//...
app.use("api", [goodsRouter]);

```
```jsx
//routes/goods.js
router.get("/", (req, res) => {
    res.send("this is rot page");
});

router.get("/goods", async (req, res) => {
    const {category} = req.query;

    const goods = await Goods.find({category});
    res.json({
        goods
    });
```
