scientific_paper_todo
=====================

### Описание

Репозиторий предназначен для помощи в оформления научной статьи. Пока информация ориентирована на Microsoft Word. Опираемся на ГОСТ (здесь номер)

Опробовано на Word 2011 для Mac OS X

### Todo для оформления статьи

1. Написать содержимое статьи, вставить все рисунки, таблицы и т.д.
1. Настроить стили текста в соответствии с правилами оформления
2. Расставить стили по тексту
2. Проверить нумерацию формул, проставить автоматическую нумерацию (**как?**) и соотнести ее со ссылками внутри текста
3. Проверить нумерацию списка литературы и ссылки в тексте, выставить автоматическую нумерацию (**как?**)
4. Заменить двойные пробелы на одинарные
  - разрывные пробелы
    - с помощью [подстановочных знаков Word] (#Использование-подстановочных-знаков-word)
      - В поле "Найти" используем `  `
      - В поле "Заменить" используем ` `
  - неразрывные пробелы
   - с помощью [подстановочных знаков Word] (#Использование-подстановочных-знаков-word)
      - В поле "Найти" используем `^s^s`
      - В поле "Заменить" используем `^s`
3. Идентифицировать все случаи физических величин с отсутствующим пробелом
  - возможны 2 ситуации: пробел нужен - `1 кВт`; пробел не нужен - `15°`
  - с помощью [подстановочных знаков Word] (#Использование-подстановочных-знаков-word)
    - В поле "Найти" используем `([0-9])([а-яА-Яa-zA-Z])`
    - В поле "Заменить" используем:
      - для случая разрывного пробела `\1 \2`
      - для случая неразрывного пробела `\1^s\2`
3. Проставить неразрывные пробелы (`alt`+`пробел` для OS X, ??? для Windows) для случаев:
  - для значений физических величин после числового значения и до единицы измерения (например, 1 кВт)
    - с помощью [подстановочных знаков Word] (#Использование-подстановочных-знаков-word)
      - В поле "Найти" используем `([0-9]) ([а-яА-Яa-zA-Z])`
      - В поле "Заменить" используем `\1^s\2`
4. Проставить неразрывные дефисы (`Сmd`+`shift`+`-` для OS X, `Сtrl`+`shift`+`-` для Windows) для случаев:
  - где может встречаться?
    - диапазоны значений (например, `... (1-7) кДж ...`)
    - ссылки на источники литературы (например, `...как показало экспериментальное исследование [1-7]...`)
    - ссылки на формулы (например, `...в системе (1-3) используется...`)
  - с помощью [подстановочных знаков Word] (#Использование-подстановочных-знаков-word)
    - В поле "Найти" используем `([0-9])-([0-9])`
    - В поле "Заменить" используем `\1^~\2`
5. Заменить все точки в физических величинах на запятые
  - с помощью [подстановочных знаков Word] (#Использование-подстановочных-знаков-word)
    - В поле "Найти" используем `([0-9]).([0-9])`
    - В поле "Заменить" используем `\1,\2`

#### Использование подстановочных знаков Word
В Word существует возможность использования подстановочных знаков (регулярных выражений) для оперирования со строками в разделе "Найти и заменить"
- Для использования подстановочных знаков необходимо:
  - Перейти в раздел "Найти и заменить"
  - Для поля замены выбрать опцию "Подстановочные знаки"
  - В поле "Найти" вбить соответствующее регулярное выражение, например `([0-9]).([0-9])`
  - В поле "Заменить" вбить соответствующее регулярное выражение, например `\1,\2`

### Полезные ссылки
1. Подстановочные знаки в Word
  - http://office.microsoft.com/ru-ru/word-help/HP005189433.aspx
  - http://asinenko.com/wp-content/uploads/2012/03/%D0%A0%D0%B5%D0%B3%D1%83%D0%BB%D1%8F%D1%80%D0%BA%D0%B8.pdf

### TODO
1. Добавить в проект шаблоны со стилями и примерами.
2. Уточнить номер ГОСТа
3. Привести регулярное выражение для поиска обычных пробелов и замены на неразрывные для физ. величин
4. Прикрутить Jekyll
5. Добавить про источники литературы по ГОСТ Р 7.0.11-2011
6. Добавить регэксп на поиск аббревиатур 
  * с целью найти, есть ли где-то расшифровки ищем просто отдельные большие буквы (равно или более двух), например `ИПУ`
  * ищем расшифровки, например `(ИПУ)`
7. Найти способ составления частотного словаря в одно действие, чтобы определять самые часто употребляемые в тексте слова (чтобы включить их в ключевые слова к статье)
