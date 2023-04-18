У нас есть глобальная переменная param = global. Будем использовать ее в запросе:

`https://postman-echo.com/get?name={{param}}`

У запроса на вкладке Tests добавим такой код:

`pm.variables.set("param", "test");`

После нажатия на кнопку Send, с каким значением параметра name будет выполнен запрос?

> "global"
