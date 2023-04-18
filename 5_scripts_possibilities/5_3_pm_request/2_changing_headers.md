# Изменение заголовков

Используя pm.request.headers мы можем изменять заголовки, отправляемые в запросе. У нас есть возможность добавлять и
удалять заголовки, а также менять значения уже существующих. Давайте сначала добавим два заголовка к нашему запросу:

+ custom-header1: custom-value1
+ custom-header2: custom-value2

Эти заголовки пригодятся нам позже.

```javascript
pm.request.headers.add({
  key: "headerName",
  value: "headerValue"
});
```

С помощью метода `add()` мы можем добавить новый заголовок к нашему запросу. В качестве параметра мы передаем пару
ключ-значение, в которой содержится название заголовка и его значение.

`pm.request.headers.remove("headerName");`

Используя метод `remove()` мы можем удалить заголовок с именем `headerName` из запроса.

```javascript
pm.request.headers.upsert({
  key: "headerName",
  value: "headerNewValue"
});
```

С помощью метода `upsert()` мы можем добавить заголовок к нашему запросу. Если заголовок с таким именем уже существует,
его значение обновится. В качестве параметра мы передаем пару ключ-значение, в которой содержится название заголовка и
его значение. Добавим к нашему запросу следующий код:

```javascript
pm.request.headers.add({
  key: "custom-header3",
  value: "custom-value3"
});
pm.request.headers.remove("custom-header1");
pm.request.headers.upsert({
  key: "custom-header2",
  value: "custom-value4"
});
```

Первый вызов добавляет к запросу новый заголовок с именем “custom-header3”. Второй удалит существующий заголовок с
именем “custom-header1”. Третий вызов обновит значение для заголовка с именем “custom-header2”.
