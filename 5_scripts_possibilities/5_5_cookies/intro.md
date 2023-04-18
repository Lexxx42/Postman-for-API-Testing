# Работа с cookies

Основные свойства и методы для работы cookies находятся в объекте `pm.cookies`. Основные методы - это `has()`, `get()` и
`toObject()`. Давайте рассмотрим их подробнее.

`pm.cookies.has(cookieName);`

С помощью метода `has()` мы проверяем есть ли cookie с таким именем.
Имя передается во входящем параметре cookieName. Если
cookie с таким именем присутствует, возвращается значение `true`, иначе вернется `false`.

`pm.cookies.get(cookieName);`

Метод `get()` возвращает нам значение cookie с заданным именем, которое передается во входящем параметре `cookieName`.
Если cookie с таким именем нет, функция вернет `undefined`.

`pm.cookies.toObject();`

С помощью метода `toObject()` можно вернуть все cookie в виде объекта. Это может быть полезно при отладке запросов.
Добавим к нашему запросу, на вкладке `Tests` такой код:

```javascript
console.log(pm.cookies.has("sails.sid"));
console.log(pm.cookies.has("sails.sid2"));

console.log(pm.cookies.get("sails.sid"));
console.log(pm.cookies.get("sails.sid2"));

console.log(pm.cookies.toObject());
```

Cookie с именем `sails.sid` существует, с именем `sails.sid2` отсутствует.
В первом блоке мы вызываем метод `has()` для
них обеих. Затем тоже самое делаем для метода `get()`.
В конце выводим в консоль все cookie. Вывод в логах у нас выглядит следующим образом:

```
true 
false
 
s:kQDoWRThsk66bl3RvU1ckqdMugEPbSTE.hlQkxTcmfaBeoK0uZVlnrC6x2nQGzOoZtLTrEYRgtXE
undefined

{sails.sid: "s:kQDoWRThsk66bl3RvU1ckqdMugEPbSTE.hlQkxTcmfaBeoK0uZVlnrC6x2nQGzOoZtLTrEYRgtXE"}
```

Для существующей куки метод `has()` вернул значение `true`, для несуществующей `false`. Первый вызов метода `get` вернул
значение куки с именем `sails.sid`, второй вызов вернул `undefined`, т.к. куки с именем `sails.sid2` отсутствует.
