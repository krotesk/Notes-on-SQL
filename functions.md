# Встроенные функции MySQL

В SQL имеется пять встроенных функций: `COUNT`, `SUM`, `AVG`, `MAX` и `MIN`. Они выполняют различные действия над результатами операто­ра `SELECT`. Функция `COUNT` работает вне зависимости от типа данных столбца, а функции `SUM`, `AVG`, `МАХ` и `MIN` оперируют только числовыми столбцами (Integer, Numeric и т.д.).

Функция `COUNT` подсчитывает количество строк в результате, а функ­ция `SUM` вычисляет сумму значений числового столбца. Например, следу­ющий SQL-оператор подсчитывает количество строк в таблице `ARTIST`:

```
SELECT COUNT(*) FROM ARTIST;
```

Результатом этого оператора является следующее отношение:

```
8
```

Как уже говорилось ранее, результатом SQL-оператора `SELECT` всегда является отношение. Если, как в данном случае, результат представляет собой одиночное число, это число все равно считается отношением, имею­щим одну строку и один столбец.

Рассмотрим следующие два оператора:

```
SELECT COUNT(Nationality) FROM ARTIST;
```

и

```
SELECT COUNT(DISTINCT Nationality) FROM ARTIST;
```

Результатом первого оператора будет отношение `8`

Результатом первого оператора будет отношение `5`

Разница в ответах возникает потому, что второй оператор `SELECT` не учитывает повторяющиеся строки.

Вот еще один пример использования встроенных функций:

```
SELECT MIN(SalesPrice), MAX(SalesPrice), SUM(SalesPrice)
FROM TRANSACTION
WHERE TransactionID < 125;
```

Результатом будет следующая таблица:

```
9750      73500  165950
```

Кроме случая с использованием ключевых слов `GROUP BY` (см. да­лее), имена столбцов не могут смешиваться со встроенными функциями. Например, следующий оператор недопустим:

```sql
SELECT CustomerlD, SUM(SalesPrice)
FROM TRANSACTION
WHERE TransactionID < 125;
```

## Строковые функции SQL Server

| Функции                                                      | Описание                                                     |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [ASCII](https://html5css.ru/sql/func_sqlserver_ascii.php)    | Возвращает код числа, представляющий конкретный символ       |
| [CHAR](https://html5css.ru/sql/func_sqlserver_char.php)      | Возвращает символ ASCII на основе кода чисел                 |
| [CHARINDEX](https://html5css.ru/sql/func_sqlserver_charindex.php) | Возвращает расположение подстроки в строке                   |
| [CONCAT](https://html5css.ru/sql/func_sqlserver_concat.php)  | Объединяет две или более строк                               |
| [Concat with +](https://html5css.ru/sql/func_sqlserver_concat_with_plus.php) | Объединяет две или более строк                               |
| [DATALENGTH](https://html5css.ru/sql/func_sqlserver_datalength.php) | Возвращает длину выражения (в байтах)                        |
| [LEFT](https://html5css.ru/sql/func_sqlserver_left.php)      | Извлекает подстроку из строки (начиная с левого)             |
| [LEN](https://html5css.ru/sql/func_sqlserver_len.php)        | Возвращает длину указанной строки                            |
| [LOWER](https://html5css.ru/sql/func_sqlserver_lower.php)    | Преобразует строку в нижний регистр                          |
| [LTRIM](https://html5css.ru/sql/func_sqlserver_ltrim.php)    | Удаление начальных пробелов из строки                        |
| [NCHAR](https://html5css.ru/sql/func_sqlserver_nchar.php)    | Возвращает символ Юникода на основе кода чисел               |
| [PATINDEX](https://html5css.ru/sql/func_sqlserver_patindex.php) | Возвращает расположение массива в строке                     |
| [REPLACE](https://html5css.ru/sql/func_sqlserver_replace.php) | Заменяет последовательность символов в строке другим набором символов |
| [RIGHT](https://html5css.ru/sql/func_sqlserver_right.php)    | Извлекает подстроку из строки (начиная справа)               |
| [RTRIM](https://html5css.ru/sql/func_sqlserver_rtrim.php)    | Удаляет замыкающие пробелы из строки                         |
| [SPACE](https://html5css.ru/sql/func_sqlserver_space.php)    | Возвращает строку с заданным количеством пробелов            |
| [STR](https://html5css.ru/sql/func_sqlserver_str.php)        | Возвращает строковое представление числа                     |
| [STUFF](https://html5css.ru/sql/func_sqlserver_stuff.php)    | Удаляет последовательность символов из строки, а затем вставляет  другую последовательность символов в строку, начиная с указанной позиции |
| [SUBSTRING](https://html5css.ru/sql/func_sqlserver_substring.php) | Извлекает подстроку из строки                                |
| [UPPER](https://html5css.ru/sql/func_sqlserver_upper.php)    | Преобразует строку в верхний регистр                         |

------

------

## Числовые функции SQL Server

| Функции                                                      | Описание                                                     |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [ABS](https://html5css.ru/sql/func_sqlserver_abs.php)        | Возвращает абсолютное значение числа                         |
| [AVG](https://html5css.ru/sql/func_sqlserver_avg.php)        | Возвращает среднее значение выражения                        |
| [CEILING](https://html5css.ru/sql/func_sqlserver_ceiling.php) | Возвращает наименьшее целое значение, превышающее или равное числу |
| [COUNT](https://html5css.ru/sql/func_sqlserver_count.php)    | Возвращает число выражения                                   |
| [FLOOR](https://html5css.ru/sql/func_sqlserver_floor.php)    | Возвращает наибольшее целочисленное значение, равное или меньшее числа |
| [MAX](https://html5css.ru/sql/func_sqlserver_max.php)        | Возвращает максимальное значение выражения                   |
| [MIN](https://html5css.ru/sql/func_sqlserver_min.php)        | Возвращает минимальное значение выражения                    |
| [RAND](https://html5css.ru/sql/func_sqlserver_rand.php)      | Возвращает случайное число или случайное число в пределах диапазона |
| [ROUND](https://html5css.ru/sql/func_sqlserver_round.php)    | Возвращает число, округленное до определенного числа десятичных разрядов |
| [SIGN](https://html5css.ru/sql/func_sqlserver_sign.php)      | Возвращает значение, указывающее знак числа                  |
| [SUM](https://html5css.ru/sql/func_sqlserver_sum.php)        | Возвращает суммированное значение выражения                  |

------

## Функции даты SQL Server

| Функции                                                      | Описание                                                     |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [CURRENT_TIMESTAMP](https://html5css.ru/sql/func_sqlserver_current_timestamp.php) | Возвращает текущую дату и время                              |
| [DATEADD](https://html5css.ru/sql/func_sqlserver_dateadd.php) | Возвращает дату после добавления определенного интервала времени/даты |
| [DATEDIFF](https://html5css.ru/sql/func_sqlserver_datediff.php) | Возвращает разницу между двумя значениями даты на основе заданного интервала |
| [DATENAME](https://html5css.ru/sql/func_sqlserver_datename.php) | Возвращает указанную часть заданной даты в виде строкового значения |
| [DATEPART](https://html5css.ru/sql/func_sqlserver_datepart.php) | Возвращает указанную часть заданной даты в виде целочисленного значения |
| [DAY](https://html5css.ru/sql/func_sqlserver_day.php)        | Возвращает день месяца (от 1 до 31) на заданную дату         |
| [GETDATE](https://html5css.ru/sql/func_sqlserver_getdate.php) | Возвращает текущую дату и время                              |
| [GETUTCDATE](https://html5css.ru/sql/func_sqlserver_getutcdate.php) | Возвращает текущую дату и время в формате UTC                |
| [MONTH](https://html5css.ru/sql/func_sqlserver_month.php)    | Возвращает месяц (от 1 до 12) на заданную дату               |
| [YEAR](https://html5css.ru/sql/func_sqlserver_year.php)      | Возвращает год (как четырехзначный номер) для данной даты    |

------

## Функции преобразования SQL Server

| Функции                                                      | Описание                                             |
| ------------------------------------------------------------ | ---------------------------------------------------- |
| [CAST](https://html5css.ru/sql/func_sqlserver_cast.php)      | Преобразует выражение из одного типа данных в другой |
| [CONVERT](https://html5css.ru/sql/func_sqlserver_convert.php) | Преобразует выражение из одного типа данных в другой |

------

## Расширенные функции SQL Server

| Функции                                                      | Описание                                                     |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [COALESCE](https://html5css.ru/sql/func_sqlserver_coalesce.php) | Возвращает первое выражение, не являющееся null, в списке    |
| [CURRENT_USER](https://html5css.ru/sql/func_sqlserver_current_user.php) | Возвращает имя текущего пользователя в базе данных SQL Server |
| [ISDATE](https://html5css.ru/sql/func_sqlserver_isdate.php)  | Возвращает 1, если выражение является допустимой датой, в противном случае 0 |
| [ISNULL](https://html5css.ru/sql/func_sqlserver_isnull.php)  | Позволяет возвращать альтернативное значение, если выражение имеет значение null |
| [ISNUMERIC](https://html5css.ru/sql/func_sqlserver_isnumeric.php) | Возвращает 1, если выражение является допустимым числом, в противном случае 0 |
| [NULLIF](https://html5css.ru/sql/func_sqlserver_nullif.php)  | Сравнивает два выражения                                     |
| [SESSION_USER](https://html5css.ru/sql/func_sqlserver_session_user.php) | Возвращает имя пользователя текущего сеанса в базе данных SQL Server |
| [SESSIONPROPERTY](https://html5css.ru/sql/func_sqlserver_sessionproperty.php) | Возвращает параметр для заданного параметра сеанса           |
| [SYSTEM_USER](https://html5css.ru/sql/func_sqlserver_system_user.php) | Возвращает сведения о имени входа для текущего пользователя в базе данных SQL Server |
| [USER_NAME](https://html5css.ru/sql/func_sqlserver_user_name.php) | Возвращает имя пользователя в базе данных SQL Server         |



# SQL Операторы

------

## Арифметические операторы SQL

| Оператор | Описание  |      |
| -------- | --------- | ---- |
| +        | Добавить  |      |
| -        | Вычесть   |      |
| *        | Умножить  |      |
| /        | Разделить |      |
| %        | Формы     |      |

------

## Побитовые операторы SQL

| Оператор | Описание                  |
| -------- | ------------------------- |
| &        | Побитовое и               |
| \|       | Побитовое или             |
| ^        | Побитовое монопольное или |

------

## Операторы сравнения SQL

| Оператор | Описание         |      |
| -------- | ---------------- | ---- |
| =        | Равно            |      |
| >        | Больше           |      |
| <        | Менее            |      |
| >=       | Больше или равно |      |
| <=       | Меньше или равно |      |
| <>       | Не равно         |      |

------

------

## Операторы соединения SQL

| Оператор | Описание                        |
| -------- | ------------------------------- |
| +=       | Добавить равно                  |
| -=       | Вычитание равно                 |
| *=       | Умножить равно                  |
| /=       | Разделить равно                 |
| %=       | По модулю равен                 |
| &=       | Побитовое и равно               |
| ^-=      | Побитовое монопольное равенство |
| \|*=     | Побитовое или равно             |

------

## Логические операторы SQL

| Оператор | Описание                                                     |      |
| -------- | ------------------------------------------------------------ | ---- |
| ALL      | Значение true, если все значения подчиненного запроса удовлетворяют условию |      |
| AND      | Значение true, если все условия разделены и истинны          |      |
| ANY      | Значение true, если любой из значений подчиненного запроса удовлетворяет условию |      |
| BETWEEN  | Значение true, если операнд находится в диапазоне сравнений  |      |
| EXISTS   | Значение true, если вложенный запрос возвращает одну или несколько записей |      |
| IN       | Значение true, если операнд равен одному из списка выражений |      |
| LIKE     | Значение true, если операнд соответствует шаблону            |      |
| NOT      | Отображает запись, если условие (ы) не соответствует действительности |      |
| OR       | Значение true, если любое из условий, разделенных или истинно |      |
| SOME     | Значение true, если любой из значений подчиненного запроса удовлетворяет условию |      |