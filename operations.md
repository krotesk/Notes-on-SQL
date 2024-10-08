# Операции

## Добавление данных

```
INSERT INTO tablename (column_name1,column_name2) VALUES(15,col1*2);
```
ВСТАВИТЬ имя_таблицы (столбец1,столбец2) ЗНАЧЕНИЯ(...,...);

## Изменение данных

```
UPDATE tablename SET column_name = 'ext-queues,500,1' WHERE id = 1;
```
ОБНОВИТЬ имя_таблицы УСТАНОВИТЬ значение столбца на .... ГДЕ id = 1;

## Удаление данных

```
DELETE FROM tablename [WHERE условие_удаления]
```

## Выборка данных

```
SELECT * FROM tablename [WHERE условие [AND ещё условие]];
```
ОТОБРАЗИТЬ * (все столбцы) ДЛЯ таблицы [ГДЕ условие [И ещё условие]];

С сортировкой:
```
SELECT * FROM tablename [WHERE условие [AND ещё условие]] ORDER BY column_name [ASC | DESC];
```

Сортировка может производиться как по возрастанию, так и по убыванию значений.

* Параметр `ASC` (по умолчанию) устанавливает порядок сортирования во возрастанию, от меньших значений к большим.
* Параметр `DECS` устанавливает порядок сортирования по убыванию, от больших значений к меньшим.

Оператор `GROUP BY` используется для объединения результатов выборки по одному или нескольким столбцам.

```
SELECT * FROM tablename GROUP BY column_name;
```

Результатом будет или сложение или иная функция (среднее, минимальное, максимальное) для одноименных объектов в данном столбце.

Оператор `HAVING` фильтрует значения, полученные в результате группировки — то есть работает не с новыми полями, а с результатом вычислений. Его записывают после `GROUP BY`.
Все операторы, с которыми вы знакомы, можно комбинировать с `HAVING` — но только при условии, что в запросе есть группировка `GROUP BY`. Без неё `HAVING` работать не будет.

## Изменение типа данных для столбца

```
ALTER TABLE tablename MODIFY columnname <datetype>;
```
