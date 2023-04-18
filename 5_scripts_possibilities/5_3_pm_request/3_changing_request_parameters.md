# Изменение параметров запроса

Следующие два метода позволяют менять параметры строки запроса.

`pm.request.addQueryParams("param1=value1");`

С помощью метода `addQueryParams()` мы можем добавить параметр в строку запроса. Он принимает на вход строку,
содержащую новый параметр и его значение.

`pm.request.removeQueryParams("param1");`

Метод `removeQueryParams()` позволяет нам удалить параметр из строки запроса. Передаваемое значение - это имя параметр,
который требуется удалить.

Если мы немного изменим наш изначальный запрос, и добавим к нему два query параметра:

```
POST https://postman-echo.com/post?param1=value1&param2=value2
```

Затем на вкладке pre-request добавим следующий код:

```javascript
pm.request.addQueryParams("param3=value3");
pm.request.removeQueryParams("param1");
```

Нажав кнопку `Send`, мы увидим что в запросе
мы передавали два параметра строки запроса: `param2=value2` и `param3=value3`.
