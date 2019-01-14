# Организация кода

**БЭМ**

О БЭМ (Блок, Элемент, Модификатор)
http://getbem.com/

.menu

.menu_item

.menu_item--active

**SMACSS**

Base Rules 
Layout Rules
Modules rules
State rules
Theme rules

_Base Rules_ - стили основных элементов сайта - body, input, button,ul, ol и др. reset.css

```css
body {
    padding:0;
    margin:0;
}

a {
    text-decoration:none;
}

a:hover {
    text-decoration:underline;
}
```

_Layot Rules_ - стили макета - здесь находятся стили глобальных элементов - шапки, футера, сайдбара и т.п.

```css
#header,#article,#footer {
    width:960px;
    margin:0 auto;
}

#article {
    border: solid #CCC;
    border-width:1px 0 0;
}
```

_Module rules_ - стили модулей - блоков, которые могут несколько раз использоваться на странице.

```css
.media {
    padding:10px;
}

.media .caption {
    font-size:20px;
}
```

_State rules_ - стили состояния - прописываются различные состояния модулей и скелета сайта. Добавляется префикс is-

```css
.is-selected {
    background-color:lightgrey;
}
```

_Theme rules_ - описываются стили оформлений

```css
//in module-name.css
.mod {
    border:1px solid;
}

//in theme.css
.mod {
    border-color:blue;
}
```


**Полезное чтиво:**

1. Основные соглашения по SMACSS 
https://github.com/Chainers/steepshot-web/wiki/SMACSS
2. Примеры кода на SMACSS
https://codepen.io/jackw/pen/apVzYo


**OOCSS**

**Принципы Объектно Ориентированного CSS**

1. Отделяем структуру от внешнего вида
То есть выносим оформление в отдельные классы и комбинируем со структурными.

2. Как следствие, не создаем селекторов привязаных к расположению. То есть не должно быть селекторов вида

```css
.header h2 {
}

.footer h2 {
}
```
то есть h2 элемент должен выглядеть одинаково, что в хедере, что в футере.

**Полезное чтиво:**

1. https://github.com/stubbornella/oocss/wiki 
2. https://www.keycdn.com/blog/oocss
3. http://thesassway.com/intermediate/using-object-oriented-css-with-sass


CSS Lint - проверка кода
https://css-tricks.com/stylelint/


**Полезное чтиво:**

1. Слова, часто используемые в CSS-классах
https://github.com/yoksel/common-words

2. Полезные подходы к именованию CSS-классов
https://habrahabr.ru/post/303174/

3. Семантика в HTML
https://css-tricks.com/semantic-class-names/

4. О CSS-архитектуре
https://web-standards.ru/articles/css-architecture/

5. Елизавета Селиванова и Ирина Левина о различных стандартах CSS 
https://html5.by/blog/bem-amcss-oocss-atomiccss-opor-mcss-smacss-fun-docssa-video/

6. Обзор различных методологий
https://habrahabr.ru/post/256109/

7. Обзор различных методологий
http://frontender.info/starting-css/

8. Согласование принципов OOCSS и SMACSS через препроцессоры https://medium.com/@stepanovv.ru/%D0%BF%D1%80%D0%B0%D0%B2%D0%B8%D0%BB%D1%8C%D0%BD%D1%8B%D0%B9-css-oocss-smacss-bem-%D0%B8-sass-49351a119283

9. Организация CSS с использованием препроцессоров и сборщиков
https://medium.freecodecamp.org/how-to-get-better-at-writing-css-a1732c32a72f 

10. Импорт CSS внутрь JavaScript, с помощью Webpack
https://habrahabr.ru/post/276417/

**Практика:**

1. Сгенерировать классы в стиле БЭМ для меню и его элементов.

2. Сгенерировать классы в стиле БЭМ для отображения товара в интернет-магазине для названия товара, цены и его картинки.

3. Формируем классы в стиле SMACSS для верха Airbnb
