# flexbox

Ранее мы уже рассмотрели систему верстки на inline-block элементах. Теперь давайте рассмотрим flexbox-верстку, то есть систему "гибких" блоков.

Для старта создадим контейнер

```css
.container {
    display: flex; /* или inline-flex */
}
```

Теперь все вложенные блоки стали "flex", то есть применение flex-свойств для контейнера будет воздействовать и на них. Также для блоков становятся доступны отдельные flex-свойства.

Важно помнить, что flex-контейнер по умолчанию обжимается по ширине контента, поэтому ширину нужно задавать явно.

Создадим внутри контейнера блок и рассмотрим его поведение

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<link rel="stylesheet" href="style.css">
</head>
<body>
	<div class="container">
		<div class="flex_block"></div>
	</div>
</body>
</html>
```

css к этому шаблону

```css
.container {
	display: flex;
	background-color: lightgrey;
}

.flex_block {
	background-color: cornflowerblue;
	height: 200px;
}
```

Несмотря на то, что блок находится внутри контейнера, мы его не видим, потому ни ширину, ни flex-basis мы не задали. Разберемся как исправить эту ситуацию.


**Поведение flex-блоков**

Резберемся как теперь поменялось поведение вложенных блоков

**flex-basis** 

Мы можем сжимать и растягивать блок, но в каком именно состоянии мы находимся будет определять flex-basic. То есть, если ширина блока стала меньше flex-basic - сначит он сжимается, если больше,то растягивается.

Добавим flex-basis:700px; в наш flex_block и посмотрим, что получится

```css
.flex_block {
	background-color: cornflowerblue;
	height: 200px;
	flex-basis:700px;
}
```
При этом при расширении блок будет оставаться 700px, но вот, если экран станет уже 700px, то блок начнет сжиматься вместе с экраном.

**flex-grow** - определяет как будет распределятся избыточное пространство между ширинами блока. 0 - значение по умолчанию, то есть блок никак не расширяется, если даже есть пространство.

По сути с появлением flex-grow блок начинает занимать свободное от flex-basis'a пространство. flex-grow показывает какую часть этого свободного пространства мы заберем.


**flex-shrink** - определяет как распределяется "негативное" пространство\(то есть сколько пикселей нам не хватает, чтобы полностью разместить все блоки по ширине\) между ширинами блоков. 1 - значение по умолчанию и его можно только уменьшать. 0 - будет означать, что ширина блока не изменяется при сжатии. Т.е. мы негативное пространство умножаем на коэфициент, указанный в flex-shrink.

**Пример**

Теперь попробуем разобраться как работают эти свойства на [примере](https://codepen.io/dmitrytinitilov/pen/rPagPN).

Сделаем четыре блока и обернем каждый в контейнер, чтобы они не влияли друг на друга.


```html
	<div class="container">
		<div class="flex_block">
		</div>
	</div>

	<div class="container">
		<div class="fluid_block">
		</div>
	</div>

	<div class="container">
		<div class="half_fluid_block">
		</div>
	</div>

	<div class="container">
		<div class="fixed_block">
		</div>
	</div>
```

Добавим необходимый CSS

Все контейнеры будут display:flex

```css
.container {
    display: flex;
    background-color: lightgrey;
}
```

**flex_block**(синий)

Блок с классом flex_block будет у нас отвечать за поведение блока внутри flex-контейнера по умолчанию, без задания свойств flex-grow и flex-shrink.

```css
.flex_block {
	background-color: cornflowerblue;
	height: 200px;
	flex-basis:700px;
}
```

Если мы посмотрим на поведение этого блока, то увидим, что когда свободное пространство есть, блок занимает ширину, указанную в flex-basis. Но при сжатии шаблона менее, чем на 700px, блок также начинает сжиматься.

**fluid_block**(фиолетовый)

fluid_block будет имитировать резиновый блок, который занимает всё свободное пространство. Правда при наличии других блоков, его поведение может отличаться от "чистого" резинового блока с шириной, заданной через %.


```css
.fluid_block {
	background-color: purple;
	height: 200px;
	flex-basis:700px;
	flex-grow:1;
	flex-shrink:1;
}
```

Мы видим, что несмотря на flex-basis:700px, fluid_block - занимает всё свободное пространство, если оно есть. При сжатии, он также сжимается вместе с контейнером.

**.half_fluid_block**(оранжевый)

Пожалуй блок с наиболее интересным поведением

```css
.half_fluid_block {
	background-color: orange;
	height: 200px;
	flex-basis:700px;
	flex-grow:0.5;
	flex-shrink:0.5;
}
```

flex-grow:0.5 заставляет забирать свободное пространство не целиком, а только его половину. Это хорошо видно рядом с flex_block и fluid_block. fluid_block забирает всё свободное пространство, flex_block никак не реагирует, а half_fluid_block забирает себе половину от разницы между fluid_block и flex_block.

![примеры разных flex-grow блоков на flexbox](pics/21_flexbox/half_flex_block.svg)

Аналогично особенности flex-shrink:0.5 можно посмотреть на примере fluid_block'a и fixed_block'a. При сжатии half_fluid_block сокращает расстояние, но в два раза меньше, чем fluid_block

![примеры разных flex-grow блоков на flexbox](pics/21_flexbox/flex_shrink.svg)


**.fixed_block**(черный)

Пример блока с фиксированной шириной, но построенного внутри flex-контейнера. Ширину блока по сути определяет в этой ситуации flex-basis. При наличии избыточного пространства блок никак не реагирует. При сжатии меньше, чем на 700px блок заставляет появиться скроллинг у окна.

```css
.fixed_block {
	background-color: black;
	height: 200px;
	flex-basis:700px;
	flex-grow:0;
	flex-shrink:0;
}
```



**flex** - обобщенное свойсво, которое задает flex-grow, flex-shrink и flex-basis одновременно.

Есть несколько специальных значений, которые позволяют еще сократить описание.

Например если нам нужен полностью резиновый блок, мы можем воспользоваться значением

```css
flex:auto;
```
тоже самое, что

```css
flex:1 1 auto;
```

то есть flex-grow и flex-shrink по единице, flex-basis auto

Если мы хотим получить блок с фиксированной шириной, без растяжения и без сжатия, то нам подойдет значение flex:none

```css
flex:none; 
```
тоже самое, что

```css
flex:0 0 auto;
```
то есть flex-grow и flex-shrink по нулям (то есть у нас нет растяжения и сжатия) и flex-basis:auto;


Резиновый блок во всю ширину экрана можно сделать вот так

```css
flex:0 0 100%;
```

**Полезное чтиво:**

1. Подробнее о интересных значениях flex:
https://css-tricks.com/almanac/properties/f/flex/

2. Наглядное объяснение, как работает flex-grow https://css-tricks.com/flex-grow-is-weird/


**Переносы в шаблонах**

**flex-wrap** - определяет как именно будут переносится блоки внутри контейнера

По умолчанию переносов нет, и мы будем видеть сжатие элементов при сжатии контейнера больше чем сумарная ширина блоков.

```css
flex-wrap: nowrap;
```

Но мы можем добиться переноса с помощью

```css
flex-wrap: wrap;
```

**Полезное чтиво:**

Разбор верстки шаблона
https://stackoverflow.com/questions/26160839/css-flex-box-layout-full-width-row-and-columns

  
**Выравнивание flex-блоков внутри контейнера**

Теперь можем задать направление flex'a

**flex-direction** определяет как именно будут располагаться блоки в контейнере и направление основной оси.

```css
flex-direction: row | row-reverse | column | column-reverse;
```

_flex-direction:row_ - располагает блоки в ряд, прижимая их к левому краю.

_flex-direction:row-reverse_ - - располагает блоки в ряд, прижимая их к правому краю.

_flex-direction: column_ - выстраивает блоки в колонку

Важный момент: при выборе значений column и column-reverse flex-basis становится

**flex-flow** - обобщенное свойство для flex-direction и flex-wrap. Например:

```css
flex-flow: row wrap
```

**justify-content** - выравнивание контента по ширине(по основной оси. При смене flex-direction на column будет выравнивать по вертикали)

justify-content: flex-start; - по левому краю

justify-content: flex-end; - по правому краю

justify-content: center; - по центру

justify-content: space-between; - распределяет избыточное расстояние равномерно между блоками. Слева и справа от блоков отступов нет.

justify-content: space-around; - распределяет пространство равномерно слева и справа от каждого блока.

**align-items** - выравнивание по вертикали(по вспомогательной оси. При смене flex-direction на column будет выравнивать по горизонтали)

_align-items: stretch_ - растягивает вложенные блоки на всю высоту контейнера.

_align-items: flex-start_ - прижимает вложенные блоки к верху контейнера.

_align-items: flex-end_ - прижимает вложенные блоки к низу контейнера

_align-items: center_

_align-items: baseline_ - выравнивает вложенные блоки по низу контента внутри них.

**align-content** - распределение контента внутри контейнера по вертикали.

**align-self** - индивидуальное выравнивание вложенного блока.

**order** - определяет порядок блоков внутри flex-контейнера. Это свойство удобно использовать в media-запросах для перестройки шаблона.

https://css-tricks.com/almanac/properties/o/order/


**Все способы вертикального выравнивания**

https://habrahabr.ru/company/netcracker/blog/277433/



**Мануалы по flexbox:**

1. Хороший мануал, с интерактивными примерами
http://html5.by/blog/flexbox/

2. Мануал от scoth [https://scotch.io/tutorials/a-visual-guide-to-css3-flexbox-properties](https://scotch.io/tutorials/a-visual-guide-to-css3-flexbox-properties)

3. Визуализация некоторых свойств flexbox [https://medium.freecodecamp.com/understanding-flexbox-everything-you-need-to-know-b4013d4dc9af#.oedaqgnkb](https://medium.freecodecamp.com/understanding-flexbox-everything-you-need-to-know-b4013d4dc9af#.oedaqgnkb)

4. Статья по flexbox от Smashing Magazine [https://www.smashingmagazine.com/2016/02/the-flexbox-reading-list/](https://www.smashingmagazine.com/2016/02/the-flexbox-reading-list/)

5. [https://paulrobertlloyd.com/2016/03/logical\_flexbox](https://paulrobertlloyd.com/2016/03/logical_flexbox)

6. Мануал от CSS-tricks [https://css-tricks.com/snippets/css/a-guide-to-flexbox/](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)


**Интересное чтиво**
1. 11 вещей, которые я узнал читая спецификацию по flexbox
https://hackernoon.com/11-things-i-learned-reading-the-flexbox-spec-5f0c799c776b
2. Примеры шаблонов сделанных на flexbox
http://learnlayout.com/flexbox.html
3. Принудительный перенос flex-блоков https://stackoverflow.com/questions/29732575/line-break-in-multi-line-flexbox

4. Приклеенный футер на flex
https://philipwalton.github.io/solved-by-flexbox/demos/sticky-footer/

5. flexbox-техники, о которых строит знать
https://habr.com/ru/post/302130/

6. Генерация выпадающего меню на flexbox
https://scrimba.com/p/pRB9Hw/cgwQ8C6

7. Игра, которая помогает разобраться с flexbox https://flexboxfroggy.com/#ru

**Практика:**

1. Создаем шаблон на весь экран с резиновыми сайдбаром и  контентом  
![сайдбар, контент](pics/02_inline_and_block_elements/sidebar_content.gif)

2. Создаем шаблон из предыдущего задания, но с фиксированным сайдбаром и резиновым контентом.

3. Создаем с двумя фиксированными сайдбарами и контентом

4. Резиновый шаблон с двумя фиксированными колонками по бокам
![хедер, два сайдбара, контент](pics/02_inline_and_block_elements/grail.gif)

5. Создаем резиновый сайт\(на всю ширину экрана\) с тремя блоками \(см рисунок\)  
![хедер, сайдбар, контент](pics/02_inline_and_block_elements/sidebar_content_menu.gif)

6. Есть четыре блока с фоновыми картинками, занимающие всю ширину экрана. Сделать, чтобы при наведении на блок, он расширялся, уменьшая ширину остальных.

7. Выровнять блок по середине экрана.

8. Сделать блок во весь экран

9. Выровнять несколько строчек по середине блока (по вертикали и горизонтали)

10. Сделать меню, в котором элементы меню разной ширины, но на одинаковом расстоянии друг от друга.

11. Сделать шаблон с четырьмя колонками, где колонки резиновые, но на одинаковом расстоянии друг от друга

12. Делаем шаблон с приклеенным футером

13. Макет: центральная область(серые блоки) должна быть фиксированной, а синяя полоска резиновой.
    ![Макет с центральным меню](pics/03_margin_and_paddings/maket2.gif)

14. Есть контент и правый сайдбар. При сужении сайдбар должен переходить наверх.

15. Используем flex-direction, чтобы горизонтальное меню превращалось в вертикальное при переходе в мобильную версию.

16. Сделать чтобы при сжатии горизонтального меню элементы уходили под кнопку "Больше" и помещались в выпадающее меню



