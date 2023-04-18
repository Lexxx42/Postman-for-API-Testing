# Локальные переменные

Работа с локальными переменными происходит таким же образом, только теперь мы используем `variables`.

```javascript
pm.variables.has("count")
pm.variables.get("count")
pm.variables.set("count", 3)
```

Область видимости локальной переменной ограничивается текущим запросом.

```javascript
console.log("(Local, before change) count = " + pm.variables.get("count"))
pm.variables.set("count", 18);
console.log("(Local, after change) count = " + pm.variables.get("count"))
```

Если мы поменяем значение локальной переменной, оно будет доступно только внутри текущего запроса. При следующем
запуске, информация о нем исчезнет.

```
1й запуск:
(Local, before change) count = 5
(Local, after change) count = 18

2й запуск:
(Local, before change) count = 5
(Local, after change) count = 18
```
