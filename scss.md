# SCSS

Документация на русском
http://sass-scss.ru/documentation/

**Переменные на SCSS**
http://codepen.io/dmitrytinitilov/pen/egZQey

**Работа с цветом**

http://prgssr.ru/development/estetichnyj-sass-chast-2-cveta-i-palitry.html

**if-else**
http://codepen.io/dmitrytinitilov/pen/mRPadV

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

**Ссылка на родителя**

https://sass-scss.ru/documentation/rasshirenie_css/ssilka_na_roditelya_selektora.html

```scss
#main {
  color: black;
  a {
    font-weight: bold;
    &:hover { color: red; }
  }
}
```
компилируется в 

```css
#main {
  color: black; }
  #main a {
    font-weight: bold; }
    #main a:hover {
      color: red; }
```

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



**Просто красивые примеры:**

https://codepen.io/HugoGiraudel/pen/nGsqr

https://codepen.io/HugoGiraudel/pen/GkCuq

**Полезное чтиво:**

1. Как использовать SASS
https://golosay.net/how-to-use-sass/

2. Сборка SCSS с помощью Gulp
https://golosay.net/gulp-setup-and-settings/

3. Настройка NPM и NodeJS для Sass
https://webdesign.tutsplus.com/ru/tutorials/watch-and-compile-sass-in-five-quick-steps--cms-28275

4. Создание конического градиента   
    https://css-tricks.com/conical-gradients-css/

**Практика:**

1. Вывести блоки. Пронумеровать их. Вывести номера внутри блоков.
2. Вывести разноцветные блоки. Цвета указаны в списке
