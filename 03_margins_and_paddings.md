# Отступы

![Поля, отступы, границы](pics/03_margin_and_paddings/margins_padding_border.gif)

**Padding** – «внутренний» отступ(выводится внутри границы). На padding распространяется цвет фона контента. Ширина padding’a добавляется к ширине и высоте контента

Мы можем задавать padding множеством способов
```css
padding: 25px 50px 75px 100px;
```
верхний padding равен 25px
padding справа равен 50px
bottom снизу равен 75px
padding слева равен 100px

```css
padding: 25px 50px 75px;
```
верхний padding равен 25px
padding'и справа и слева равны 50px
нижний padding равен 75px

```css
padding: 25px 50px;
```
top and bottom paddings are 25px
right and left paddings are 50px

```css
padding: 25px;
```
all four paddings are 25px
Мы можем задавать padding отдельно по направлениям
padding-bottom
Устанавливает padding снизу
padding-left
Устанавливает padding слева
padding-right
Устанавливает padding справа
padding-top
Устанавливает padding сверху


**Margin**

margin – внешний отступ(делает отступ снаружи границы). Margin всегда прозрачен
Правила использования margin’a, аналогичны padding’у – просто слово padding меняется на margin



margin:0px; у body убирает белые отступы по краям документа

margin:0 auto; – выравнивает блок по середине

**Границы**

border - это граница блока. В отличии от margin и padding мы можем задать цвет для border'a. Также как в случае с margin и padding ширина border'a добавляется к ширине блока.

Мы можем написать все свойства границы сразу, задав ширину, стиль (solid - это непрерывная граница), цвет.

```css
border: 3px solid black;
```

А можем задавать их по отдельности:

```css
border-width:3px; // ширина
border-style:solid; // стиль
border-color:red; // цвет
```

Мы можем задавать границу отдельно по направлениям

```css
border-top:1px dotted red; //сверху граница красными точками
border-bottom-style: dashed;
```

outline – граница, которая возникает вокруг объекта, при его выборе курсором. Синтаксис outline аналогичен border'у. Например:

```css
outline:1px dotted grey;
```

Для чего же кроме border нам может понадобиться еще и outline!? Во-первых, мы можем отключить выделение у объекта, которое в отличии от границы не скругляется. Во-вторых outline - очень удобная вещь при отладки верстки, так как outline не сдвигает верстку, а накладывается на нее.

**Практика:**

1)	Сделать один блок под другим. Между ними сделать расстояние высотой в один блок. Оба блока должны быть выровнены по центру

![Один блок под другим](pics/03_margin_and_paddings/two_blocks.gif)




2)	Есть три блока в линию, с небольшими отступами между ними. Выровнять всю эту конструкцию по центру.

![Три блока в ряд](pics/03_margin_and_paddings/three_blocks.gif)


3)	Сделать вот такую конструкцию и выровнять ее по центру


![Блоки змейкой](pics/03_margin_and_paddings/four_blocks.gif)



4)  Сделать вот такой вот макет


![Макет с хедером и футером](pics/03_margin_and_paddings/maket.gif)

5) Три ячейки одна на другой с границами



