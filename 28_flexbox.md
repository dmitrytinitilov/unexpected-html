# flexbox

Для старта создадим контейнер

```css
.container {
    display: flex; /* или inline-flex */
}
```

Теперь все вложенные блоки стали "flex", то есть применение flex-свойств для контейнера будет воздействовать и на них. Также для блоков становятся доступны отдельные flex-свойства.

Важно помнить, что flex-контейнер по умолчанию обжимается по ширине контента, поэтому ширину нужно задавать явно.

**Поведение flex-блоков**

Резберемся как теперь поменялось поведение вложенных блоков

**flex-basis** - аналог min-width для flex-элемента

**flex-grow** - определяет как будет распределятся избыточное пространство между ширинами блока. 1 - значение по умолчанию, но мы можем заставить ширину блока расти в три раза быстрее, поставив 3. Без flex-grow блок не растягивается.

**flex-shrink** - определяет как распределяется "негативное" пространство\(то есть сколько пикселей нам не хватает, чтобы полностью разместить все блоки по ширине\) между ширинами блоков. 1 - значение по умолчанию и его можно только уменьшать. 0 - будет означать, что ширина блока не изменяется при сжатии. Т.е. мы негативное пространство умножаем на коэфициент, указанный в flex-shrink.

**flex** - обобщенное свойсво, которое задает flex-grow, flex-shrink и flex-basis одновременно.

Есть несколько специальных значений, которые позволяют еще скоратить описание.

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

**flex-direction** определяет как именно будут располагаться блоки в контейнере.

```css
flex-direction: row | row-reverse | column | column-reverse;
```

_flex-direction:row_ - располагает блоки в ряд, прижимая их к левому краю.

_flex-direction:row-reverse_ - - располагает блоки в ряд, прижимая их к правому краю.

_flex-direction: column_ - выстраивает блоки в колонку



**flex-flow** - обобщенное свойство для flex-direction и flex-wrap. Например:

```css
flex-flow: row wrap
```

**justify-content** - выравнивание контента по ширине

justify-content: flex-start; - по левому краю

justify-content: flex-end; - по правому краю

justify-content: center; - по центру

justify-content: space-between; - распределяет избыточное расстояние равномерно между блоками. Слева и справа от блоков отступов нет.

justify-content: space-around; - распределяет пространство равномерно слева и справа от каждого блока.

**align-items** - выравнивание по вертикали

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



**Дополнительные ссылки:**

Хороший мануал, с интерактивными примерами
http://html5.by/blog/flexbox/

[https://scotch.io/tutorials/a-visual-guide-to-css3-flexbox-properties](https://scotch.io/tutorials/a-visual-guide-to-css3-flexbox-properties)

[https://medium.freecodecamp.com/understanding-flexbox-everything-you-need-to-know-b4013d4dc9af#.oedaqgnkb](https://medium.freecodecamp.com/understanding-flexbox-everything-you-need-to-know-b4013d4dc9af#.oedaqgnkb)

[https://www.smashingmagazine.com/2016/02/the-flexbox-reading-list/](https://www.smashingmagazine.com/2016/02/the-flexbox-reading-list/)

[https://paulrobertlloyd.com/2016/03/logical\_flexbox](https://paulrobertlloyd.com/2016/03/logical_flexbox)

[https://css-tricks.com/snippets/css/a-guide-to-flexbox/](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

**Интересное чтиво**
1. 11 вещей, которые я узнал читая спецификацию по flexbox
https://hackernoon.com/11-things-i-learned-reading-the-flexbox-spec-5f0c799c776b
2. Примеры шаблонов сделанных на flexbox
http://learnlayout.com/flexbox.html
3. Принудительный перенос flex-блоков https://stackoverflow.com/questions/29732575/line-break-in-multi-line-flexbox

**Практика:**

1. Создаем шаблон на весь экран с резиновыми сайдбаром и  контентом  
![сайдбар, контент](pics/02_inline_and_block_elements/sidebar_content.gif)

2. Создаем шаблон из предыдущего задания, но с фиксированным сайдбаром и резиновым контентом.

3. Создаем с двумя фиксированными сайдбарами и контентом

4. Резиновый шаблон с двумя фиксированными колонками по бокам
![хедер, два сайдбара, контент](pics/02_inline_and_block_elements/grail.gif)

5. Создаем резиновый сайт\(на всю ширину экрана\) с тремя блоками \(см рисунок\)  
![хедер, сайдбар, контент](pics/02_inline_and_block_elements/sidebar_content_menu.gif)

6. Есть контент и правый сайдбар. При сужении сайдбар должен переходить наверх.

7. Выровнять блок по середине экрана

8. Сделать резиновую галерею на флексах

9. Макет: центральная область(серые блоки) должна быть фиксированной, а синяя полоска резиновой.

    ![Макет с центральным меню](pics/03_margin_and_paddings/maket2.gif)

9. Сделать меню, в котором элементы меню на каком-то расстоянии друг от друга

10. Сделать адаптивный шаблон с использованием flex-box

11. Сделать чтобы при сжатии горизонтального меню элементы уходили под кнопку "Больше" и помещались в выпадающее меню



