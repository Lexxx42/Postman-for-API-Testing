У нас есть запрос, содержащий два query параметра:

```
POST https://postman-echo.com/post?param1=value&param2=value
```

На вкладке pre-request мы добавили следующий код:

```
pm.request.removeQueryParams("value");
```

Нажав кнопку Send, какие query параметры мы отправим в запросе?

> param1=value и param2=value
