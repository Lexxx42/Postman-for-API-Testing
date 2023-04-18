# Взаимодействие с запросом через pm.request

Для работы с данными запроса в скриптах можно воспользоваться объектом `pm.request`.
Нам потребуется добавить в коллекцию новый запрос:

```
POST https://postman-echo.com/post
```

```
Body:
{
    "var": "value"
}
```

Для начала рассмотрим несколько полезных свойств объекта `pm.request`.

`pm.request.method`

Данное свойство содержит HTTP метод запроса.

`pm.request.url`

Свойство содержит url запроса.

`pm.request.headers`

Это свойство содержит список заголовков запроса.

`pm.request.body`

Данное свойство содержит тело запроса. Добавим к нашему запросу следующий код, на вкладку pre-request:

```javascript
console.log("Request method : " + pm.request.method);
console.log("Request url : " + pm.request.url);
console.log("Request headers : " + pm.request.headers);
console.log("Request body : " + pm.request.body);
```

После нажатия на кнопку Send в консоли мы увидим такой вывод:

```
Request method : POST
Request url : https://postman-echo.com/post
Request headers : 
Request body : {
    "var": "value"
}
```
