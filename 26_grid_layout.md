#Grid Layout

```css
.wrapper {
    display: grid;
}
```

Сделаем следующий html

```html
<div class="wrapper">
    <div class="item1"></div>
    <div class="item2"></div>
    <div class="item3"></div>
    <div class="item4"></div>
    <div class="item5"></div>
    <div class="item6"></div>
</div>
```

**grid-template-columns, grid-template-rows**

Мы можем задать сетку через ширины столбцов и строк

```css
.wrapper {
    display: grid;
    grid-template-columns: 100px 100px 100px;
    grid-template-rows: 50px 50px;
}
```

Естественно, что столбцы и строки необязательно должны занимать одинаковую ширину

```css
.wrapper {
    display: grid;
    grid-template-columns: 200px 50px 100px;
    grid-template-rows: 100px 30px;
}
```

**grid-column-start, grid-column-end**

В предыдущем примере каждый наш блок занимал ровно одну ячейку. А что если мы хотим, чтобы блок занял несколько ячеек? Один из подходов состоит в том, чтобы задавать старт и конец блока. При этом мы нумеруем не сами колонки, а границы между ними. 

```css
.item1 {
    grid-column-start: 1;
    grid-column-end: 4;
}
```

Можно задавать также распределение по рядам grid-row-start и grid-row-end

```css
.item1 {
    grid-column-start:1;
    grid-column-end:3;
    grid-row-start:1;
    grid-row-end:3;
}
```

Это блок будет занимать 4-ре ячейки

**grid-gap**

Если мы хотим задать расстояние между ячейками, используем свойство grid-gap

```css
grid-gap: 5px;
```

**grid-template-areas**

https://developer.mozilla.org/ru/docs/Web/CSS/grid-template-columns

Еще один подход состоит в том, что мы можем задать области через маркеры(какие-нибудь символы), а в дальнейшем указать каким областям, какие маркеры соответствуют



```html
<div class="container">
    <div class="header"></div>
    <div class="content"></div>
</div>
```

Зададим области через grid-template-areas




```css
.container {
    display: grid;
    grid-gap: 5px;    
    grid-template-columns: 100%;
    grid-template-rows: 50px 350px;
    grid-template-areas:
        "h"
        "c";
}
```

И через grid-area укажем, каким областям что соответствует

```css
.header {
	background-color: cornflowerblue;
	grid-area: h;
}

.content {
	background-color: lightgrey;
	grid-area: c;
}
```


Еще один пример. Зададим 12 колонок. Будем пользоваться конструкцией repeat(12,fr), чуть позже рассмотрим детальнее её значение.

```css
.container {
    display: grid;
    grid-gap: 5px;    
    grid-template-columns: repeat(12, 1fr);
    grid-template-rows: 50px 350px 50px;
    grid-template-areas:
        "h h h h h h h h h h h h"
        "m m c c c c c c c c c c"
        "f f f f f f f f f f f f";
}
```

Теперь укажем какие маркеры соответствуют каким областям

```css
.header {
    grid-area: h;
}

.menu {
    grid-area: m;
}

.content {
    grid-area: c;
}

.footer {
   grid-area: f;
}
```

Если мы не хотим заполнять какие-то области, то в этих местах лучше проставить точки

```css
grid-template-areas:
        ". h h h h h h h h h h ."
        "c c c c c c c c c c m m"
        ". f f f f f f f f f f .";

```


Не забудьте использовать эмодзи для обозначения областей! :)

**1fr**

fr - это резиновый юнит. Считаем сколько у нас в строке свободного пространства и распределяем его равномерно между fr'ами.

```css
.container {
  grid-template-columns: 1fr 1fr 40px 2fr;
  grid-template-rows: 100px 200px 100px;
}
```

В данном примере мы берем ширину контейнера, отнимаем от нее 40px, делим оставшееся пространство на 4 (потому что у нас 1fr+1fr+2fr =4fr) и распределяем его в соответствии с количеством fr в колонках


**Полезное чтиво:**

1. Учим CSS-гриды за 5 мин
https://habrahabr.ru/company/edison/blog/343614/

2. Как быстро спроектировать сайт с помощью CSS-grid
https://habrahabr.ru/company/edison/blog/343796/

3. Примеры разных гридов
https://gridbyexample.com/examples/

4. Про fr-unit
https://alligator.io/css/css-grid-layout-fr-unit/

5. grid-template-areas
https://alligator.io/css/css-grid-layout-grid-areas/

6. Пример с использованием emoji в  grid-template-areas 
https://codepen.io/Guilh/pen/peNKqy

7. Стандарт
https://www.w3.org/TR/css-grid/

8. Вариант учебного пособия от css-tricks
https://css-tricks.com/snippets/css/complete-guide-grid/

9. Настройка сеток на реальных сайтах
https://www.maketea.co.uk/2016/09/28/css-grid-layout-is-a-step-change.html

10. Пример использования grid'ов
https://bitsofco.de/3-new-css-features-to-learn-in-2017/?utm_source=forwebdev&utm_medium=announcement&utm_campaign=tri-novye-vozmozhnosti-css--kotorye-stoit

11. Примеры сайтов на гридах
https://webflow.com/blog/webflow-sites-built-with-css-grid

12. Игра, которая помогает разобраться с grid'ами
http://cssgridgarden.com/#ru

**Практика:**

1. Сделать сайт из трех колонок
2. Сделать шаблон, приведенный ниже
![хедер и три колонки](pics/layouts/three_columns.svg)
3. Сделать наш шаблон из трех блоков на основе grid'ов  
![хедер, сайдбар, контент](pics/02_inline_and_block_elements/sidebar_menu_content.svg)
4. Сделать шаблон, используя grid-template-area  
![хедер, сайдбар, контент](pics/grids/grid_cells.svg)
5. Сделать шаблон, где сайдбар имеет фиксированную ширину, а контент резиновый
![боковая панель и контент](pics/layouts/sidebar_content.svg)
6. Сделать, чтобы при сужении окна правый сайдбар становился хедером
![боковая панель и контент](pics/layouts/content_right_sidebar.svg)


