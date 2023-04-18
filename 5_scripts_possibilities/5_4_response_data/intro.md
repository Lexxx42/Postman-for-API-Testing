# Получение данных ответа в Postman

Работать с ответом от сервера в скриптах мы можем с помощью объекта pm.response. Далее мы рассмотрим его основные
свойства и методы.

`pm.response.code`

В свойстве pm.response.code содержится код ответа. Например 200 или 404.

`pm.response.status`

Это свойство содержит описание статуса. Это может быть например OK или Not found.

`pm.response.headers`

В этом свойстве записаны все заголовки, полученные в ответе.

`pm.response.responseTime`

Свойство pm.response.responseTime содержит время ответа от сервера в миллисекундах.

`pm.response.responseSize`

Свойство pm.response.responseSize содержит размер ответа от сервера.

`pm.response.text();
pm.response.json();`

В этих свойствах содержится тело ответа в текстовом формате и json формате соответственно. На вкладке Tests добавим к
нашему запросу следующий код:

```javascript
console.log("Code: " + pm.response.code);
console.log("Status: " + pm.response.status);
console.log("Time: " + pm.response.responseTime);
console.log("Size: " + pm.response.responseSize);
console.log("Headers: " + pm.response.headers);
```

Здесь мы последовательно выводим в консоль: код ответа, описание статуса, время и размер ответа от сервера, а также
заголовки, содержащиеся в ответе. Нажмем на кнопку Send и отправим запроса на сервер. Открыв консоль мы увидим
следующее:

```
Code: 200
Status: OK
Time: 219
Size: 727
Headers: Date: Wed, 06 Jul 2022 08:28:13 GMT↵
Content-Type: application/json; charset=utf-8↵
Content-Length: 727↵
Connection: keep-alive↵
ETag: W/"2d7-FzzE5s00KWdI8fc4+p1p6UcHQ7w"↵
Vary: Accept-Encoding↵
set-cookie: sails.sid=s%3AJow9vkWX5EnaMlH7uTjiqMiDM8urNYK7.rg3hZXtV6VLQ1N4ReTITXcfxUuHlLMV9RIeM2FOL7P8; Path=/; HttpOnly↵
```
