# HW_2 Postman


http://162.55.220.72:5005/first
1. Отправить запрос.
2. Статус код 200
3. Проверить, что в body приходит правильный string.

```javascript
//Статус код 200
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

//Проверить, что в body приходит правильный string
pm.test("Body is correct", function () {
    pm.response.to.have.body("This is the first responce from server!ss");
});
```
