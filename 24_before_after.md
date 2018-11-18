# До и после. Селекторы :before :after


```css
p.box {
   width: 300px;
   border: solid 1px black;
   height:80px;
   line-height:80px;
}

p.box:before {
   content: "#";
   border: solid 1px black;
   padding: 10px;
   margin: 0 10px 0 0;
}
```

Реализация примера
http://codepen.io/anon/pen/LNpZgB


**Полезное чтиво:**

1. Популярно о псевдоэлементах :Before и :After http://habrahabr.ru/post/154319/

2. Интересные кнопки с помощью :before :after
http://tympanus.net/codrops/2012/01/11/css-buttons-with-pseudo-elements/

3. Всплывающие подсказки на чистом CSS https://medium.freecodecamp.org/a-step-by-step-guide-to-making-pure-css-tooltips-3d5a3e237346 

4. Различные применения before, after
https://codemyviews.com/blog/the-lowdown-on-before-and-after-in-css

5. Пример сайта со "скошенной" версткой с помощью before и after https://www.securitywithoutborders.org/

6. Много различных примеров для заголовков и текста http://archie-goodwin.net/load/specializirovannye_blogi/webmaster/css_psevdo_ehlementy_before_i_after_na_praktike/24-1-0-407


**Значение url()**

```css
.box:before {
   content:url('image.jpg');
}
```

**Значение attr()**

1. Подробнее об использовании attr в content'e
https://developer.mozilla.org/ru/docs/Web/CSS/attr
2. Примеры использования attr
https://davidwalsh.name/css-content-attr


**Счетчики counter()**

Свойство counter-reset инициализирует счетчик. Это свойство как правило ставится в блок, который встречается один раз, например в body.

counter-increment свойство, которое занимается увеличением счетчика

content:counter() - позволяет нам вывести значения счетчика

```css
body {
   counter-reset: my-awesome-counter;
}
div {
   counter-increment: my-awesome-counter;
}
div:before {
   content: counter(my-awesome-counter);
}
```

Мы можем увеличивать счетчик более, чем на единицу

```css
li
{
   list-style-type: none;
}

ol
{
   counter-reset: mysupercounter; 
}

li:before {
   counter-increment: mysupercounter 2;
   content: counter(mysupercounter) ". ";
}
```

Задаем стилистику для счетчика

```css
div:before {
  content: counter(my-awesome-counter, upper-roman);
}
```

**Полезное чтиво:**

1. Примеры с счетчиками
https://css-tricks.com/numbering-in-style/

2. Счетчики блоков на чистом css https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Counters

3. Подробно о различных вариантах counter-increment https://developer.mozilla.org/en/docs/Web/CSS/counter-increment


**CSS-Shapes**

**Практика:**

1.	Создание кавычек вокруг блоков текста
2.	Добавление картинок до и после блоков с текстом
3.	Кнопки составленные из двух-трех частей
4.	Эффект стопки картинок
5.      Сделать блок трапецию
6.	Сделать, чтобы при наведении на картинку весь остальной сайт затемнялся
7.	Эффекты с тенями
8.	Создаем блок с иконкой внутри
9.	Создаем кнопки с автоматической нумерацией (состоящие из двух частей)
10.	Создаем блоки с автоматической нумерацией (римская нумерация)
11.	Поставить разные счетчики для блоков разных цветов



