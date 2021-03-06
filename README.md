# HTML:
1. Табуляция: 4 пробела.

2. Доктайп: ```<!DOCTYPE html>```

3. Кодировка utf-8: ```<meta charset="utf-8">```

4. Для удобства работы с IE используются conditional comments:
  ```
  <!--[if IE 7]>         <html class="lt-ie9 lt-ie8"> <![endif]-->
  <!--[if IE 8]>         <html class="lt-ie9"> <![endif]-->
  <!--[if gt IE 8]><!--> <html> <!--<![endif]-->
  ```
5. Скрипты подключаются внизу документа (исключение составляют modernizr, html5shiv).

6. Инлайн стили не используются.


# CSS:
1. Табуляция: 4 пробела.

2. Селекторы: по возможности следует использовать селекторы классов и избегать контекстных зависимостей. 

3. Именование: 
  * cелекторы именуются в нижнем регистре;
  * при использовании методологии БЭМ имеет смысл опустить префиксы наподобие b-, т. к. они ухудшают визуальное восприятие кода.
  
4. Форматирование: 
  * каждый селектор записывается с новой строки;
  * после селектора следует единичный пробел и открывается фигурная скобка;
  * каждое свойство со значением записывается на новой строке и имеет отступ в один таб (4 пробела);
  * после значения обязательно наличие точки с запятой;
  * фигурная скобка закрывается на новой строке;
  * блоки отделяются друг от друга пустой строкой.
  
  Пример: 
  ```
  selector {
    property1: value1;
    property2: value2;
  }

  selector2 {
    property3: value3;
    property4: value4;
  }
  ```
  
5. Группировка свойств:

| Box model           | Position | Background            | Typography & Table          | Etc.              |
|---------------------|----------|-----------------------|-----------------------------|-------------------|
| border-radius       | position | background            | border-collapse             | content           |
| box-sizing          | top      | background-color      | border-spacing              | counter-increment |
| box-shadow          | right    | background-image      | caption-side                | counter-reset     |
| border              | bottom   | background-repeat     | color                       | cursor            |
| clear               | left     | background-attachment | font                        | opacity           |
| clip                | z-index  | background-position   | font-family                 | resize            |
| display             |          | background-size       | font-size                   | visibility        |
| float               |          | background-clip       | font-stretch                |                   |
| height (min-, max-) |          | background-origin     | font-style                  |                   |
| width (min-, max-)  |          |                       | font-variant                |                   |
| margin              |          |                       | font-weight                 |                   |
| padding             |          |                       | letter-spacing              |                   |
| outline             |          |                       | line-height                 |                   |
| overflow            |          |                       | list-style                  |                   |
|                     |          |                       | list-style list-style-image |                   |
|                     |          |                       | list-style-position         |                   |
|                     |          |                       | list-style-type             |                   |
|                     |          |                       | quotes                      |                   |
|                     |          |                       | text-align                  |                   |
|                     |          |                       | text-decoration             |                   |
|                     |          |                       | text-indent                 |                   |
|                     |          |                       | text-overflow               |                   |
|                     |          |                       | text-shadow                 |                   |
|                     |          |                       | text-transform              |                   |
|                     |          |                       | vertical-align              |                   |
|                     |          |                       | white-space                 |                   |
|                     |          |                       | word-spacing                |                   |
|                     |          |                       | word-wrap                   |                   |
  
6. Префиксы: 
  * если в требованиях значатся акутульные версии браузеров, то имеет смысл убедиться в необходимости вендорных префиксов. К примеру, border-radius можно использовать без префиксов (http://caniuse.com/#search=border-radius). Актуальная информация доступна на http://caniuse.com/;
  * вендорные префиксы записываются ДО свойства со значением.
  
  Пример:
  ```
  -webkit-transform: rotate(1deg);
      -ms-transform: rotate(1deg);
          transform: rotate(1deg);
  ```

7. !important не используется.


# Sass:
1. В качестве синтаксиса используется SCSS.

2. При использовании сторонних библиотек, к примеру compass, следует проверить, что поступает в генерируемый css. Возможно наличие избыточных вендорных префиксов. В таком случае следует настроить конфиги.


# JavaScript (jQuery):
1. Табуляция: 4 пробела.

2. При подключении скриптов внизу документа использование JavaScript событий DOMContentLoaded, load либо метода jQuery .ready является избыточным.

3. Если в требованиях значатся IE8+ либо IE9+ и предполагается минимум кода, то имеет смысл отказаться от использования jQuery и посмотреть в сторону нативных решений (http://youmightnotneedjquery.com/).
