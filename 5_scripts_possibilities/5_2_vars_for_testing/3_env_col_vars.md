# Переменные коллекции, окружения и данных

Для переменных коллекции работа с переменными происходит таким же образом, только вместо `globals` мы теперь используем
`collectionVariables` и работаем с переменными текущей коллекции.

```javascript
pm.collectionVariables.has("count");
pm.collectionVariables.get("count");
pm.collectionVariables.set("count", 3);
pm.collectionVariables.unset("count");
pm.collectionVariables.replaceIn("Count = {{count}}");
pm.collectionVariables.clear();
```

Аналогично для переменных выбранного окружения будут использоваться такие функции:

```javascript
pm.environment.has("count");
pm.environment.get("count");
pm.environment.set("count", 3);
pm.environment.unset("count");
pm.environment.replaceIn("Count = {{count}}");
pm.environment.clear();
```

Для переменных уровня данных вызов аналогичных функций будет выглядеть таким образом:

```javascript
pm.iterationData.has("count");
pm.iterationData.get("count");
pm.iterationData.unset("count");
```

Добавим к нашему запросу такой код:

```javascript
console.log("(Global) count = " + pm.globals.get("count"))
console.log("(Collection) count = " + pm.collectionVariables.get("count"))
console.log("(Environment) count = " + pm.environment.get("count"))
```

В первой строке кода мы выводим значение глобальной переменной `count`. Затем выводим значение переменной заданной на
уровне коллекции. В последней строке в вывод попадет значение переменной из текущего окружения `local`.

```
(Global) count = 3 
(Collection) count = 10 
(Environment) count = 5
```

Вызвав наш запрос, в консоли мы увидим, что значение глобальной переменной равно 3. Переменная коллекции содержит
значение 10, а переменная окружения 5.
