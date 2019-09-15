# Препроцессоры. SCSS

**Настройка Gulp**

Инициализируем окружение. При этом создается файл с описанием нашей конфигурации package.json

```
npm init --yes
```

Добавляем gulp в зависимости разработки

```
npm install --save-dev gulp
```

Добавляем модуль для gulp-sass

```
npm install gulp-sass --save-dev
```

Теперь создадим файл gulpfile.js

```js
var gulp = require('gulp');
var sass = require('gulp-sass');

//Задача для сборки
gulp.task('sass', function () {
  return gulp.src('./sass/**/*.scss')
    .pipe(sass().on('error', sass.logError))
    .pipe(gulp.dest('./css'));
});
```


Для запуска Gulp через командную строку нужно поставить gulp-cli

```
npm install -g gulp-cli
```

И далее набрать, чтобы началась сборка SASS и SCSS

```
gulp sass
```

**Автоматическое отслеживание изменений**

Для автоматической сборки нам нужно настроить задачу gulp.task('watch')

```js
var gulp = require('gulp');
var sass = require('gulp-sass');

//Задача для сборки
gulp.task('sass', function () {
  return gulp.src('./sass/*.scss')
    .pipe(sass().on('error', sass.logError))
    .pipe(gulp.dest('./css'));
});

gulp.task('watch', function () {
  gulp.watch('./sass/*.scss', gulp.series('sass'));
});
```

После этого в командной строке запускаем 

```
gulp watch
```

Держим командную строку открытой. При изменении нашего SCSS, должен автоматически собираться CSS

**Переменные на SCSS**

В SСSS мы можем задавать переменные через $

```scss
$primary_color : violet;

.block {
  width:300px;
  height:200px;
  background-color:$primary_color;
}
```

**Переменные в calc**

Для отображения переменной внутри calc нужно обернуть ее в конструкцию #{ }
```css
   height: calc(100% - #{$body_padding})
```


**Вложенность в SCSS**

https://getinstance.info/articles/css/sass-basics-nesting/

```sass
.block{
    font-size:20px;
    p {
      font-weight:bold;
    }
}
```

Преобразуется в

```css
.block {
  font-size:20px;
}

.block p {
  font-weight:bold;
}
```


**Ссылка на родителя**

https://sass-scss.ru/documentation/rasshirenie_css/ssilka_na_roditelya_selektora.html

```scss
a {
    font-weight: bold;
    &:hover { color: red; }
}
```
компилируется в 

```css
a {
    font-weight: bold; 
}

a:hover {
    color: red;
}
```

еще пример

```sass
.col {
    &-span1 { width: 8.33%; }
    &-span2 { width: 16.66%; }
    &-span3 { width: 24.99%; }
}
```
Преобразуется в

```css
.col-span1 { width: 8.33%; }
.col-span2 { width: 16.66%; }
.col-span3 { width: 24.99%; }
```

То есть этот подход идеально подходит для BEM'a

**@media-запросы в SASS**

http://thesassway.com/intermediate/responsive-web-design-in-sass-using-media-queries-in-sass-32

```sass
$small: 320px;
$large: 1200px;

.avatar {
  width: 250px;
  @media screen and (max-width: $small) {
    width: 100px;
  }
  @media screen and (min-width: $large){
    width:500px;
  }
}
```

```css
.avatar {
  width: 250px;
}
@media screen and (max-width: 320px) {
  .avatar {
    width: 100px;
  }
}
@media screen and (min-width: 1200px) {
  .avatar {
    width:500px;
  }
}
```


**Миксины**

https://sass-scss.ru/documentation/miksini/obyavlenie_miksina.html

```scss
@mixin large-text {
  font: {
    family: Arial;
    size: 20px;
    weight: bold;
  }
  color: #ff0000;
}

.page-title {
  @include large-text;
  padding: 4px;
  margin-top: 10px;
}
```

**Миксины с параметрами**

```scss
@mixin headline ($color, $size) {
    color: $color;
    font-size: $size;
}

h1 {
    @include headline(green, 12px);
}
```


**Работа с цветом**

http://prgssr.ru/development/estetichnyj-sass-chast-2-cveta-i-palitry.html

**if-else**
http://codepen.io/dmitrytinitilov/pen/mRPadV


**Директива each**
http://sass-scss.ru/documentation/direktivi_kontrolya_i_virazheniya/direktiva_each.html

http://codepen.io/dmitrytinitilov/pen/QdNzez

**Директива for**

http://codepen.io/dmitrytinitilov/pen/BpKMGE


**Функции**

https://sass-scss.ru/documentation/funktsii/

```scss
$grid-width: 40px;
$gutter-width: 10px;

@function grid-width($n) {
  @return $n * $grid-width + ($n - 1) * $gutter-width;
}

#sidebar { width: grid-width(5); }
```

**Объединение нескольких CSS-файлов в один**

```js
const concat = require('gulp-concat');

gulp.task('sass', function() {
return gulp.src('stylesheets/**/*.scss')
  .pipe(sass())
  .pipe(concat('styles.css'))
  .pipe(gulp.dest('css'))
});
```

**Минимизация CSS**

```js
let gulp = require('gulp');
let cleanCSS = require('gulp-clean-css');
 
gulp.task('minify-css', () => {
  return gulp.src('styles/*.css')
    .pipe(cleanCSS({compatibility: 'ie8'}))
    .pipe(gulp.dest('dist'));
});
```

Сделаем так, чтобы минимизированная версия сохранялась в отдельный файл

```js
let gulp = require('gulp');
let cleanCSS = require('gulp-clean-css');
let rename = require("gulp-rename");
 
gulp.task('minify-css', () => {
  return gulp.src('styles/*.css')
    .pipe(cleanCSS({compatibility: 'ie8'}))
    .pipe(rename({
        basename: "styles",
        suffix: ".min",
        extname: ".css"
    }))

    .pipe(gulp.dest('dist'));
});
```






**Просто красивые примеры:**

https://codepen.io/HugoGiraudel/pen/nGsqr

https://codepen.io/HugoGiraudel/pen/GkCuq


**Полезное чтиво:**

1. Документация на русском
http://sass-scss.ru/documentation/

2. Как использовать SASS
https://golosay.net/how-to-use-sass/

3. Сборка SCSS с помощью Gulp
https://golosay.net/gulp-setup-and-settings/

4. Настройка NPM и NodeJS для Sass
https://webdesign.tutsplus.com/ru/tutorials/watch-and-compile-sass-in-five-quick-steps--cms-28275

5. Создание конического градиента   
    https://css-tricks.com/conical-gradients-css/
    
6. Нужли ли препроцессоры в 2018м году?
 http://andrew-r.ru/notes/preprocessors-vs-vanilla-css/
 
7. Работа с цветом в SASS
http://prgssr.ru/development/estetichnyj-sass-chast-2-cveta-i-palitry.html

8. Вложенность в SASS
https://getinstance.info/articles/css/sass-basics-nesting/

9. 16 советов по продвинутой верстке на SASS
https://proglib.io/p/advanced-scss/


**Практика:**

1. Вывести блок. Цвет и ширину блока задаем через SASS-переменные
2. Сайдбар с фиксированной шириной, контент с шириной через calc. Ширину сайдбара кидаем в переменную. При изменении значения переменной шаблон не должен разъежаться.
![сайдбар, контент](pics/02_inline_and_block_elements/sidebar_content.gif)

3. Сгенерировать систему БЭМ-классов для продукта .product, name, img, price через &

4. Создать mixin, который бы добавлял блоку скругления по краям и цвет

5. Вывести блоки. Пронумеровать их. Вывести номера внутри блоков.
6. Вывести разноцветные блоки. Цвета указаны в списке
