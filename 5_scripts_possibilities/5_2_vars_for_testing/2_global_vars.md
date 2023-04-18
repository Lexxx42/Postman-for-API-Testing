# Глобальные переменные

Для работы с переменными в скриптах чаще всего используются три функции: `has`, `get` и `set`.
С помощью метода has мы проверяем существует ли такая переменная.
Метод `get` позволяет получить значение переменной.
С помощью метода `set` можно задать значение переменной.

```javascript
pm.globals.has("count");
```

Функция `has()`, принимает на вход один параметр. В нем содержится имя глобальной переменной. Возвращаемое значение
имеет тип boolean.
Если среди глобальных переменных, есть переменная с таким именем, вернется значение `true`. Если такой
переменной нет, вернется `false`.

```javascript
console.log("Does count exist? : " + pm.globals.has("count"));
console.log("Does count2 exist? : " + pm.globals.has("count2"));
```

Если мы добавим к нашему запросу такой код и нажмём `Send`, в консоли мы увидим следующий вывод:

```
Does count exist? : true
Does count2 exist? : false
```

Т.к. мы добавили глобальную переменную `count`, вызов первой функции вернул нам `true`. Переменную с именем `count2` мы
не добавляли, поэтому второй вызов функции `has` вернул нам `false`.

```javascript
pm.globals.get("count");
```

Функция `get()`, принимает на вход один параметр. В нем содержится имя глобальной переменной. Функция вернет ее
значение. Если такой переменной нет, вернется `undefined`.

```javascript
pm.globals.set("count", 3);
```

Функция `set()`, принимает на вход два параметра. В первом передается имя глобальной переменной, во втором новое
значение. Если такой переменной нет, она создается.

```javascript
pm.globals.unset("count");
```

# !!!!

Функция `unset()`, принимает на вход один параметр. В нем содержится имя глобальной переменной. После выполнения этой
функции переменная с заданным именем будет удалена.

`pm.globals.clear();`

Если нам нужно удалить все переменные, можно вызвать функцию `clear()`.

`pm.globals.replaceIn("Global variable count = {{count}}.");`

Используя функцию `replaceIn()`, можно вернуть строку с подставленными в нее значениями переменных. Добавим к нашему
запросу такой код:

```javascript
console.log(pm.globals.replaceIn("Global variable count = {{count}}"));
console.log("Global variable count2 = " + pm.globals.get("count2"));

pm.globals.set("count", 3)
pm.globals.set("count2", 3)

console.log(pm.globals.replaceIn("Global variable count = {{count}}"));
console.log(pm.globals.replaceIn("Global variable count2 = {{count2}}"));

pm.globals.unset("count2")
console.log("Global variable count2 = " + pm.globals.get("count2"));
```

Сначала мы выводим значения переменных с именами `count` и `count2`. Затем устанавливаем им новые значения и затем уже
их снова выводим в лог. После вызова функции `unset()` переменная `count2` снова будет иметь значение `undefined`.
Нажмём кнопку `Send`. В консоли мы увидим следующий вывод:

```
Global variable count = 20
Global variable count2 = undefined

Global variable count = 3
Global variable count2 = 3

Global variable count2 = undefined
```

Сначала для переменной `count` выводится значение 20, которое было задано у нее. Для переменной `count2`, выводится
undefined, т.к. такой переменной у нас не было. После вызова функции `set`, создается переменная `count2`. Для нее
устанавливается значение 3. Значение у переменной `count` изменяется на 3.
В последних двух строках вывода мы видим, что в консоль выводятся уже новые значения этих переменных.
