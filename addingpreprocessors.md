# Добавляем препроцессоры

http://lesscss.org/
http://verekia.com/less-css/dont-read-less-css-tutorial-highly-addictive

```
<script src="less.js" type="text/javascript"></script>
<link rel="stylesheet/less" type="text/css" href="style.less">

Создание переменной
@header-font: Georgia;
h1, h2, h3, h4 { font-family: @header-font; }
.large { font-family:@header-font; }

Комментарии
/* Colors for my Website */

Локальные –глобальные  переменные
@color: #222222;
a {
    @color: #ffffff;
    color:@color;
}
button {
    background: @color;
}

Здесь ссылка будет окрашена в белый, а у кнопки будет черный фон.

Важно отметить, вопреки тому, что вы только что прочитали, переменные в LESS больше похожи на константы. Это значит, что они, в отличие от переменных, могут быть определены только один раз.

Можем задать модульную сетку
.button{ @unit: 3px; border:@unit solid #ddd; padding: @unit * 3; margin: @unit * 2; }
Интерполяция переменных
@my-selector: banner; // Usage
.@{my-selector} { 
font-weight: bold;
line-height: 40px;
margin: 0 auto;
}
Еще пример
@images: "../img";
 // Usage
body { 
color: #444;
background: url("@{images}/white-sand.png"); 
}
Наследование
a:extend(.b) {}

// the above block does the same thing as the below block
.a {
  &:extend(.b);
}
.c:extend(.d all) {
  // extends all instances of ".d" e.g. ".x.d" or ".d.x"
}
.c:extend(.d) {
  // extends only instances where the selector will be output as just ".d"
}

Множественное наследование
.e:extend(.f) {}
.e:extend(.g) {} // the above an the below do the same thing 
.e:extend(.f, .g) {}

Работа с цветом
@color: #941f1f; button { background: #941f1f + #222222; border: #941f1f - #111111; }

@color-button: #d24444; input.submit { color:#fff; background:@color-button; border:1px solid @color-button - #222; padding:5px 12px; }

@color: #faa51a; .button { background: -webkit-gradient(linear, left top, left bottom, from(@color + #151515), to(@color - #151515)); background: -moz-linear-gradient(top, @color + #151515, @color - #151515); }

Цветовые функции
@color: #3d82d1; 
.left_box { background:lighten(@color, 20%); }
.right_box { background:darken(@color, 20%); }

@color: #3d82d1;.left_box { background: desaturate(@color, 18%); }
.middle_box { background: @color; } 
.right_box { background: saturate(@color, 18%); }

@color = #167e8a;
hue(@color);
saturation(@color); 
lightness(@color);
fadein() 
fadeout()

Вложенность
article.post {
p{ margin: 0 0 12px 0; }
a { color: red; } 
a:hover { color: blue; } 
img { float:left; } 
}
Примеси (mixins)
.Rounded_top {
 -webkit-border-top-left-radius: 6px; 
-webkit-border-top-right-radius: 6px; 
-moz-border-radius-topleft: 6px; 
-moz-border-radius-topright: 6px;
 border-top-left-radius: 6px;
 border-top-right-radius: 6px; 
} 
.tab { background: #333;
 color:#fff;
 .Rounded_top; 
}
.submit { .rounded_top; }

Параметры
.button(@radius:3px, @background: #e7ba64, @padding: 4px) { .radius(@radius); background:@background; border: 1px solid @background - #222; padding: @padding; } .read_more { .button(0px); }

Смеси с параметрами
@defaultRadius:30px; //значение по умолчанию
 
.RoundedShape(@radius:@defaultRadius){
    -webkit-border-radius:@radius;
       -moz-border-radius:@radius;
            border-radius:@radius;  
}

.Round{
    .RoundedShape(9999px);
}
 
.RoundedSquare(@radius:@defaultRadius){
    .RoundedShape(@radius);
}

#shape1{
    .Round;
}
 
#shape2{
    .RoundedSquare;
}


@arguments, @rest


.mixin(@a; @rest...) { // @rest is bound to arguments after @a // @arguments is bound to all arguments }

Вложенность


#header{
    /* #header styles */
    h1{
        /* #header h1 styles */
    }
}



Случай для hover
.shape{
    &:hover{
        background:@lightRed;
    }
}




Условные операторы
(Guarding Statements)
div when(@color = #ff0000) {
  	background-color: #000;
}

& when(@color = #ff0000) {
 
  div {
	  background-color: #00f;
  }
}


Циклы

.generate-columns(4);
.generate-columns(@n, @i: 1) when (@i =< @n) { 
.column-@{i} { width: (@i * 100% / @n); 
} 
.generate-columns(@n, (@i + 1)); 
}


@iterations: 10;
.loopingClass (@index) when (@index > 0) {
	(~"#slide@{index} .imgheader") { 
        background-image: url("../img/background/block@{index}.jpg"); 
    }
	.loopingClass(@index - 1);
}
.loopingClass (0) {}
.loopingClass (@iterations);

Обновленный вариант
@iterations: 10;
.loopingClass (@index) when (@index > 0) {
#slide@{index} .imgheader { 
background-image: url("../img/background/block@{index}.jpg"); 
}

.loopingClass(@index - 1);
}

.loopingClass (0) {}
.loopingClass (@iterations);

@list-red:                             #ffebee, #ffcdd2, #ef9a9a, #e57373, #ef5350,
                                       #f44336, #e53935, #d32f2f, #c62828, #b71c1c;
Для примера, давайте создадим для каждого цвета свой класс:
.color-generator(@index: 1, @color) when (@index <= length(@list-red)) {
  // Получаем цвет по индексу
  @item: extract(@list-red, @index);

  // Конструируем класс на основе полученных данных
  .clr-@{color}-@{index} {
    color: @item;
  }

  // Рекурсия
  .color-generator(@index + 1, @color);
}

.color-generator(@color: red);

More or Less

.class-test-if {
  .if(isnumber(2), {
      .-then() {
        background-color: #fff;
      }
      .-else() {
        background-color: #000;
      }
  });
}
Случай для равно

.class-test-if {
  @variable: col;

  .if(@variable eq col, {
    .-then() {
      content: "true";
    }
    .-else() {
      content: "false";
    }
  });
}

For
.class-test-for {
  // Просто переменная, можно и без неё
  @count: 4;

  // Цикл
  .for(@count);
  .-each(@index) {
    &-@{index} {
        width: @index * (100% / @count);
    }
  }
}
Функции для работы со списками

@list: "banana", "tomato", "potato", "peach";
n: length(@list);
Output:
n: 4;

@list: apple, pear, coconut, orange;
value: extract(@list, 3);
Output:
value: coconut;




```








