# Организация кода

**БЭМ**

БЭМ - Блок, Элемент, Модификатор

Допустим мы хотим сделать меню. Нам понадобится блок с классом .menu

Вложенные пункты меню, это элементы. Для их обозначения мы используем имя блока и добавляем название самого элемента, то есть в результате получаем .menu\_item

Теперь какой-то из пунктов меню должен быть активным, и для этого у него должно быть какое-то особенное оформление. Для этого добавим класс .menu\_item--active

.menu - блок

.menu\_item - элемент

.menu\_item--active - модификатор


```html
<div class="menu">
    <div class="menu_item">
    </div>
    <div class="menu_item">
    </div>
    <div class="menu_item">
    </div>
    <div class="menu_item menu_item--active">
    </div>
</div>

```

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

_Layout Rules_ - стили макета - здесь находятся стили глобальных элементов - шапки, футера, сайдбара и т.п.

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
   [https://github.com/Chainers/steepshot-web/wiki/SMACSS](https://github.com/Chainers/steepshot-web/wiki/SMACSS)
2. Примеры кода на SMACSS
   [https://codepen.io/jackw/pen/apVzYo](https://codepen.io/jackw/pen/apVzYo)

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

1. [https://github.com/stubbornella/oocss/wiki](https://github.com/stubbornella/oocss/wiki) 
2. [https://www.keycdn.com/blog/oocss](https://www.keycdn.com/blog/oocss)
3. [http://thesassway.com/intermediate/using-object-oriented-css-with-sass](http://thesassway.com/intermediate/using-object-oriented-css-with-sass)

CSS Lint - проверка кода  
[https://css-tricks.com/stylelint/](https://css-tricks.com/stylelint/)

**Полезное чтиво:**

1. Слова, часто используемые в CSS-классах  
   [https://github.com/yoksel/common-words](https://github.com/yoksel/common-words)

2. Полезные подходы к именованию CSS-классов  
   [https://habrahabr.ru/post/303174/](https://habrahabr.ru/post/303174/)

3. Семантика в HTML  
   [https://css-tricks.com/semantic-class-names/](https://css-tricks.com/semantic-class-names/)

4. О CSS-архитектуре  
   [https://web-standards.ru/articles/css-architecture/](https://web-standards.ru/articles/css-architecture/)

5. Елизавета Селиванова и Ирина Левина о различных стандартах CSS   
   [https://html5.by/blog/bem-amcss-oocss-atomiccss-opor-mcss-smacss-fun-docssa-video/](https://html5.by/blog/bem-amcss-oocss-atomiccss-opor-mcss-smacss-fun-docssa-video/)

6. Обзор различных методологий  
   [https://habrahabr.ru/post/256109/](https://habrahabr.ru/post/256109/)

7. Обзор различных методологий  
   [http://frontender.info/starting-css/](http://frontender.info/starting-css/)

8. Согласование принципов OOCSS и SMACSS через препроцессоры [https://medium.com/@stepanovv.ru/правильный-css-oocss-smacss-bem-и-sass-49351a119283](https://medium.com/@stepanovv.ru/правильный-css-oocss-smacss-bem-и-sass-49351a119283)

9. Организация CSS с использованием препроцессоров и сборщиков  
   [https://medium.freecodecamp.org/how-to-get-better-at-writing-css-a1732c32a72f](https://medium.freecodecamp.org/how-to-get-better-at-writing-css-a1732c32a72f)

10. Импорт CSS внутрь JavaScript, с помощью Webpack  
    [https://habrahabr.ru/post/276417/](https://habrahabr.ru/post/276417/)

**Практика:**

1. Сгенерировать классы в стиле БЭМ для меню и его элементов.

2. Сгенерировать классы в стиле БЭМ для отображения товара в интернет-магазине для названия товара, цены и его картинки. Учесть, что могут быть товары с акционной ценой.

3. Формируем классы в стиле SMACSS для верха Airbnb



