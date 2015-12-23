# Добавляем CSS3

border-radius – задает радиус скругления

Можно задавать скругление отдельно по углам
Если хотим получить эллипс ставим border-radius:50%

box-shadow

box-shadow: 1px 2px 3px 4px #ccc

1px – смещение слева
2px – смещение справа
3px – радиус размытия
4px – увеличение размеров тени (padding для тени)

Цвет тени лучше делать полупрозрачным через rgba


Множественные фоны

.sample2 .sea { 
height:300px;
width:480px; 
position: relative; 
background-image: url("media/fishing.svg"), url("media/mermaid.svg"), url("media/sea.png");
background-position: top right 10px, bottom left, top left; 
background-repeat: no-repeat, repeat-x, repeat-x ;
}

**Градиенты**
```css
div {
  height: 500px;
  background-color: yellow;
  background-image:
    linear-gradient(
     110deg, 
      red, blue
    );
}
```
градусы начинаются от верха


```css
div {
  height: 100px;
  background-color: red;
  background-image:
    linear-gradient(
      to right,
      red,
      yellow 25%,
      yellow 35%,
      green 50%
    );
}
```

Редактор градиентов. http://www.colorzilla.com/gradient-editor/
http://uigradients.com/#

CSS patterns
http://lea.verou.me/css3patterns/
https://24ways.org/2011/css3-patterns-explained/


Радиальные градиенты

Повторяющиеся градиенты

Пример сайтов с градиентами
http://line25.com/articles/web-design-trend-showcase-super-gradients
