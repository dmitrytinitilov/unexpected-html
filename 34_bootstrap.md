# Bootstrap

http://www.w3schools.com/bootstrap/bootstrap_grid_examples.asp

http://webcomplex.com.ua/css/adaptivnyj-dizajn-s-pomoshhyu-bootstrap-3-grid-system-delaem-maket-sajta.html

O Bootstrap 4<BR>
https://blog.getbootstrap.com/2016/07/27/bootstrap-4-alpha-3/


**Подключение через CDN**

```html
<!-- Latest compiled and minified CSS -->
<link rel="stylesheet" href="http://maxcdn.bootstrapcdn.com/bootstrap/3.3.4/css/bootstrap.min.css">

<!-- jQuery library -->
<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.1/jquery.min.js"></script>

<!-- Latest compiled JavaScript -->
<script src="http://maxcdn.bootstrapcdn.com/bootstrap/3.3.4/js/bootstrap.min.js"></script>
```

**Минимальный скрипт**

Добавляем в body

```html
<div class="container-fluid">
  <h1>My First Bootstrap Page</h1>
  <p>This is some text.</p> 
</div>
```

.container  - контейнер с фиксированной шириной
.container-fluid – резиновый контейнер

http://stackoverflow.com/questions/22262311/container-fluid-vs-container



**Работа с сеткой**


```html
<div class="row">
  <div class="col-sm-4">.col-sm-4</div>
  <div class="col-sm-4">.col-sm-4</div>
  <div class="col-sm-4">.col-sm-4</div>
</div>
```

**Неодинаковые колонки**

```html
<div class="row">
  <div class="col-sm-4">.col-sm-4</div>
  <div class="col-sm-8">.col-sm-8</div>
</div>
```

**Вложенные колонки**

https://codepen.io/SitePoint/pen/raBPeo

**Задание смещений**

.offset*
.col-sm-offset-2

Правый блок будет смещен на колонки вправо
```html
<div class="row">
  <div class="col-sm-4">.col-sm-4</div>
  <div class="col-sm-6 col-sm-offset-2">.col-sm-6 со смещение вправо на две колонки</div>
</div>
```
**Префиксы для различных типов устройств**

Блоки ширины от 1 до 12<BR>
**xs** (для телефонов)<BR>
**sm** (для планшетов)<BR>
**md** (для десктопов)<BR>
**lg** (для больших десктопов)<BR>

Мы можем менять соотношение колонок под разные типы устойств

```html
<div class="container-fluid">
  <div class="row">
    <div class="col-sm-4 col-md-2">.col-sm-4</div>
    <div class="col-sm-8 col-md-10">.col-sm-8</div>
  </div>
</div>
```

**Breakpoints для Bootstrap'a
**

```css
/* Extra small devices (phones, less than 768px) */
/* No media query since this is the default in Bootstrap */

/* Small devices (tablets, 768px and up) */
@media (min-width: @screen-sm-min) { ... }

/* Medium devices (desktops, 992px and up) */
@media (min-width: @screen-md-min) { ... }

/* Large devices (large desktops, 1200px and up) */
@media (min-width: @screen-lg-min) { ... }
```

**Работа с картинками**
```html
<img class="img-responsive" src="img_chania.jpg" alt="Chania" width="460" height="345">
```


**Работа со шрифтами**

&lt;h1&gt; - &lt;h6&gt; - заголовки
&lt;small&gt; - второстепенный текст
&lt;mark&gt; - подсветка
&lt;abbr&gt; - подчеркивает пунктиром
&lt;blockquote&gt; - цитата
&lt;code&gt; -код
&lt;kbd&gt; - комбинации клавиш

**Работа с таблицами**

.table – обычная таблица без вертикальных ограничений
.table-striped – полосатая таблица
.table-bordered – внутренние границы
.table-hover – таблица с подсветкой рядков при наведении

**Jumbotron**

```html
<div class="container">
  <div class="jumbotron">
    <h1>Bootstrap Tutorial</h1> 
    <p>Bootstrap is the most popular HTML, CSS, and JS framework for developing
    responsive, mobile-first projects on the web.</p> 
  </div>
  <p>This is some text.</p> 
  <p>This is another text.</p> 
</div>
```

**Делаем заголовок страницы**

```html
<div class="page-header">
  <h1>Example Page Header</h1>
</div>
```

**Закругления well**

```html
<div class="well well-sm">Small Well</div>
<div class="well well-lg">Large Well</div>
```

**Стили кнопок**

.btn-default
.btn-primary
.btn-success
.btn-info
.btn-warning
.btn-danger
.btn-link

**Пример**

```html
<button type="button" class="btn btn-default">Default</button>
```

Размеры кнопок
.btn-lg
.btn-md
.btn-sm
.btn-xs
<button type="button" class="btn btn-primary btn-block">Button 1</button>
Можно задать активные и деактивированные кнопки .active .disabled

**Группы кнопок**

```html
<div class="btn-group">
  <button type="button" class="btn btn-primary">Apple</button>
  <button type="button" class="btn btn-primary">Samsung</button>
  <button type="button" class="btn btn-primary">Sony</button>
</div>
```

**Вертикальные группы кнопок**

```html
<div class="btn-group-vertical">
  <button type="button" class="btn btn-primary">Apple</button>
  <button type="button" class="btn btn-primary">Samsung</button>
  <button type="button" class="btn btn-primary">Sony</button>
</div>
```

**Выпадающее меню**

```html
<div class="btn-group">
      <button type="button" class="btn btn-primary dropdown-toggle" data-toggle="dropdown">
      Sony <span class="caret"></span></button>
      <ul class="dropdown-menu" role="menu">
        <li><a href="#">Tablet</a></li>
        <li><a href="#">Smartphone</a></li>
      </ul>
    </div>
Glyphicons
<span class="glyphicon glyphicon-envelope"></span>
Badges
<a href="#">News <span class="badge">5</span></a>
Бейдж внутри кнопки
<button type="button" class="btn btn-primary">Primary <spanclass="badge">7</span></button>
<div class="progress">
  <div class="progress-bar" role="progressbar" aria-valuenow="70"
  aria-valuemin="0" aria-valuemax="100" style="width:70%">
    <span class="sr-only">70% Complete</span>
  </div>
</div>
```


**Карусель**

Пример готовой карусели
https://www.w3schools.com/bootstrap/bootstrap_carousel.asp

```html
<div id="myCarousel" class="carousel slide" data-ride="carousel">
  <!-- Indicators -->
  <ol class="carousel-indicators">
    <li data-target="#myCarousel" data-slide-to="0" class="active"></li>
    <li data-target="#myCarousel" data-slide-to="1"></li>
    <li data-target="#myCarousel" data-slide-to="2"></li>
    <li data-target="#myCarousel" data-slide-to="3"></li>
  </ol>

  <!-- Wrapper for slides -->
  <div class="carousel-inner" role="listbox">
    <div class="item active">
      <img src="img_chania.jpg" alt="Chania">
    </div>

    <div class="item">
      <img src="img_chania2.jpg" alt="Chania">
    </div>

    <div class="item">
      <img src="img_flower.jpg" alt="Flower">
    </div>

    <div class="item">
      <img src="img_flower2.jpg" alt="Flower">
    </div>
  </div>

  <!-- Left and right controls -->
  <a class="left carousel-control" href="#myCarousel" role="button" data-slide="prev">
    <span class="glyphicon glyphicon-chevron-left" aria-hidden="true"></span>
    <span class="sr-only">Previous</span>
  </a>
  <a class="right carousel-control" href="#myCarousel" role="button" data-slide="next">
    <span class="glyphicon glyphicon-chevron-right" aria-hidden="true"></span>
    <span class="sr-only">Next</span>
  </a>
</div>
```

data-ride="carousel" обеспечивает вращение
data-interval="500" – задает скорость смены. Задавать нужно в главном div’e<BR>
Наличие класса .slide – обеспечивает скольжение при смене<BR>
Ширину картинки можно поставить через class=”carousel-inner”<BR>
Pause - Ставит показ слайдов на паузу при фокусе «карусели» и возобновляет показ при потере фокуса.
 
Добавляем **carousel-caption**

```html
<div class="item">
   <img src="img_flower2.jpg" alt="Flower">
   <div class="carousel-caption">
      <h3>Flowers</h3>
      <p>Beatiful flowers in Kolymbari, Crete.</p>
   </div>
</div>
```


**Пример верстки**
http://webcomplex.com.ua/css/adaptivnyj-dizajn-s-pomoshhyu-bootstrap-3-grid-system-delaem-maket-sajta.html


**Создание «гармошки» на Bootstrap**
http://mybootstrap.ru/javascripts/#collapse


**Практика**
1. Создание сайта с пятью картинками в два ряда
2. Создание сайта с хедером, футером, сайдбарами(грааль)
![хедер, два сайдбара, контент](pics/02_inline_and_block_elements/grail.gif)
3.Создаем резиновый сайт\(на всю ширину экрана\) с тремя блоками \(см рисунок\)
![хедер, сайдбар, контент](pics/02_inline_and_block_elements/sidebar_content_menu.gif)
4. Есть боковая колонка и блок контента. При сужении боковая панель должна переместиться на верх шаблона
![сайдбар, контент](pics/02_inline_and_block_elements/sidebar_content.gif)
<BR>![хедер, контент](pics/21_adaptive_design/content_header.gif)

5. Карусель на Bootstrap
Настройка слайдов, их размера, прокрутки и времени прокрутки

6. Верстка адаптивного макета на Bootstrap
http://www.gridelicious.com/themes/treble/demo/

**Видео-курс по Bootstrap**

https://www.youtube.com/watch?v=f7CXSxeLCik

**Полезное чтиво:**

1. Разница между Bootstrap4 и 3 https://www.quackit.com/bootstrap/bootstrap_4/differences_between_bootstrap_3_and_bootstrap_4.cfm

2. Использование flexbox в Bootstrap 4
https://medium.com/codingthesmartway-com-blog/introduction-to-bootstrap-4-flex-layout-flexbox-for-bootstrap-f85405ce5ebf

3. Альтернативный взгляд на использования jquery и bootstrap
http://frontender.info/whats-wrong-with-jquery-and-bootstrap/


