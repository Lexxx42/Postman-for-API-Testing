# Область видимости переменных

Переменные в Postman имеют различную область видимости. Это может быть полезно в зависимости от решаемых задач. Всего
есть 5 областей видимости: глобальные переменные, переменные коллекции, переменные окружения, переменные уровня данных и
локальные переменные.

Глобальные переменные позволяют получить доступ к данным между различными коллекциями, запросами, тестовыми скриптами и
окружениями. Глобальные переменные доступны внутри всего рабочего пространства. Они имеют самую широкую область
видимости из возможных в Postman.

Переменные коллекции доступны для всех запросов внутри коллекции. Они не зависят от окружения, их значения не меняются в
зависимости от выбранного окружения. Такой тип переменных удобен, если вы используете только одно окружение.

Переменные окружения позволяют организовать область видимости для работы с различными окружениями. Например у вас может
быть стенд для разработки и отдельный тестовый стенд. В разные моменты времени, каждый из них будет активным. Если у вас
только одно окружение, эффективнее будет использовать переменные коллекций.

Переменные уровня данных заполняются из внешних файлов, например csv или json. С их помощью определяются наборы данных,
которые затем можно использовать в тестовых прогонах. Они будут использованы только в качестве текущих значений, и не
сохранятся за пределами прогонов коллекции или отдельных запросов.

Локальные переменные имеют самую узкую область видимости. Это временные переменные, значения которых относятся лишь к
текущему запуску запроса или коллекции. Они перестанут быть доступны после его завершения. Также локальные переменные
подойдут, если вы хотите переопределить переменные с более широкой видимостью, без сохранения значения в переменной,
после окончания выполнения запроса.

Если у вас есть переменные с одинаковым именем в двух разных областях видимости, будет использована переменная с самой
узкой областью видимости. Если например у вас есть переменные `name` среди глобальных и локальных переменных, тогда при
запуске запроса будет использована локальная переменная.

Postman сохраняет все переменные в виде строк. При работе с объектами и массивами, не забудьте перед сохранением вызвать
JSON.stringify(), а перед получением нужно будет вызвать JSON.parse().
