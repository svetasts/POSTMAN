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


http://162.55.220.72:5005/user_info_3
1. Отправить запрос.
2. Статус код 200
3. Спарсить response body в json.
4. Проверить, что name в ответе равно name s request (name вбить руками.)
5. Проверить, что age в ответе равно age s request (age вбить руками.)
6. Проверить, что salary в ответе равно salary s request (salary вбить руками.)
7. Спарсить request.
8. Проверить, что name в ответе равно name s request (name забрать из request.)
9. Проверить, что age в ответе равно age s request (age забрать из request.)
10. Проверить, что salary в ответе равно salary s request (salary забрать из request.)
11. Вывести в консоль параметр family из response.
12. Проверить что u_salary_1_5_year в ответе равно salary*4 (salary забрать из request)

```javascript
//Статус код 200
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

//Спарсить response body в json
 let jsonData = pm.response.json();

//Проверить, что name в ответе равно name s request (name вбить руками.)
pm.test("name", function () {
    pm.expect(jsonData.name).to.eql("Sveta");
});
//Проверить, что age в ответе равно age s request
pm.test("age", function () {
    pm.expect(jsonData.age).to.eql("37");
});
//Проверить, что salary в ответе равно salary s request 
pm.test("salary", function () {
    pm.expect(jsonData.salary).to.eql(5000);
});

//Спарсить request
let req = request.data;
console.log("req", req)

//Проверить, что name в ответе равно name s request (name забрать из request.)
pm.test("name", function () {
    pm.expect(jsonData.name).to.eql(req.name);
});

//Проверить, что age в ответе равно age s request (age забрать из request.)
pm.test("age", function () {
    pm.expect(jsonData.age).to.eql(req.age);
});
//Проверить, что salary в ответе равно salary s request (salary забрать из request.)
pm.test("salary", function () {
    pm.expect(jsonData.salary).to.eql(req.salary * 1);
});

//Вывести в консоль параметр family из response.
console.log("family", jsonData.family)

//Проверить что u_salary_1_5_year в ответе равно salary*4 (salary забрать из request)
pm.test("salary_1_5", function() {
    pm.expect(jsonData.family.u_salary_1_5_year).to.eql(req.salary * 4);
});
```

http://162.55.220.72:5005/object_info_3
1. Отправить запрос.
2. Статус код 200
3. Спарсить response body в json.
4. Спарсить request.
5. Проверить, что name в ответе равно name s request (name забрать из request.)
6. Проверить, что age в ответе равно age s request (age забрать из request.)
7. Проверить, что salary в ответе равно salary s request (salary забрать из request.)
8. Вывести в консоль параметр family из response.
9. Проверить, что у параметра dog есть параметры name.
10. Проверить, что у параметра dog есть параметры age.
11. Проверить, что параметр name имеет значение Luky.
12. Проверить, что параметр age имеет значение 4.
