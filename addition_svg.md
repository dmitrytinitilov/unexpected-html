# SVG


**Работа с простейшими фигурами**

http://serganbus.github.io/d3tutorials/svg_primer.html

http://css.yoksel.ru/svg-shapes/

Давайте создадим наш первый SVG

```html
<svg width="500" height="50">
  <circle cx="250" cy="25" r="25"> 
</svg>
```

В результате получим черный круг размером 50 на 50px

Добавим к кругу характеристики

```html
<svg width="500" height="50">
  <circle cx="250" cy="25" r="25" fill="yellow" stroke="orange"/> 
</svg>
```

Мы можем также воздействовать на отдельные элементы с помощью CSS

```html
<svg width="500" height="50">
  <circle cx="250" cy="25" r="25" class="pumpkin"/> 
</svg>
```

```css
.pumpkin {
    fill: yellow;
    stroke: orange;
    stroke-width: 5;
 }
```

**path**

Описание синтаксиса линий<BR>
http://www.w3schools.com/graphics/svg_path.asp

Подробное описание<BR>
https://developer.mozilla.org/ru/docs/Web/SVG/Tutorial/Paths

Просто хорошее описание<BR>
http://css.yoksel.ru/svg-path/

**Комбинирование фигур**

https://sarasoueidan.com/blog/structuring-grouping-referencing-in-svg/

_Тэг &lt; g>_

тег g позволяет группировать различные фигуры в один объект.

_Тэг &lt; defs&gt;_<BR>
http://tutorials.jenkov.com/svg/defs-element.html

С помощью тега &lt; defs&gt; можно создавать фигуры, которые будут образами для других элементов

В дальнейшем эти элементы можно использовать с помощью тега &lt; use&gt;

http://tutorials.jenkov.com/svg/use-element.html

**Работа с текстом**

https://developer.mozilla.org/ru/docs/Web/SVG/Element/textPath

http://vanseodesign.com/web-design/svg-text-on-a-path-part-1/

```html
<svg width="660" height="220" style="outline: 1px solid red; font-size: 2em; overflow: visible;">

  <defs>  
    <path id="text-path" d="M225,150 v-80 h240 v80 Z" />  
  </defs>

  <text>  
    <textPath xlink:href="#text-path" >SVG text on a linear path</textPath>  
  </text>

</svg>
```

Примеры текстовых эффектов на SVG
https://codepen.io/collection/DPYwYN/2/

**Заливка и обводка**

http://css.yoksel.ru/svg-fill-and-stroke/#stroke-dasharray

**Фильтры и маски**

*Фильтры в SVG*
http://html5.by/blog/svg-filters/

*Изменение цвета SVG*
https://codepen.io/noahblon/post/coloring-svgs-in-css-background-images

*Наложение фонов в надписях*
http://thenewcode.com/633/Boom-Wham-Pow-Comic-Book-FX-Lettering-with-SVG-Filters

```css
.icon-blue {
    -webkit-filter: hue-rotate(220deg) saturate(5);
    filter: hue-rotate(220deg) saturate(5);
}
```

**Градиенты в SVG**

```html
<svg width="120" height="120" xmlns="http://www.w3.org/2000/svg">
    <defs>
        <linearGradient id="MyGradient">
            <stop offset="5%"  stop-color="green"/>
            <stop offset="95%" stop-color="gold"/>
        </linearGradient>
    </defs>

    <rect fill="url(#MyGradient)"
          x="10" y="10" width="100" height="100"/>
</svg>
```
**Паттерны**

https://developer.mozilla.org/en-US/docs/Web/SVG/Element/pattern


**Анимация в SVG**

```html
<svg width="120" height="120" viewPort="0 0 120 120" version="1.1"
     xmlns="http://www.w3.org/2000/svg">
  
  <rect x="10" y="10" width="100" height="100">
    <animate attributeType="XML" attributeName="x" from="-100" to="120"
        dur="10s" repeatCount="indefinite"/>
  </rect>
</svg>
```

**Движение по кривой**

http://primat.org/news/svg_animacija_dvizhenie_po_krivoj/2016-03-25-1162

**Адаптивность в SVG**

*Адаптивное лого на SVG*
http://blog.cloudfour.com/responsive-logo-composition-with-svg/


**viewBox**

https://svg-art.ru/?p=5


**Примеры:**

Checkbox на SVG<BR>
http://codepen.io/SaraSoueidan/pen/40433575e3d0d026c7d9c00eb45522a1

**Проверка SVG на ошибки**

https://jakearchibald.github.io/svgomg/


**Дополнительные ссылки**

*Дизайн шрифтов с помощью SVG*
http://thenewcode.com/633/Boom-Wham-Pow-Comic-Book-FX-Lettering-with-SVG-Filters

*Красивые эффекты на SVG*
http://css-live.ru/cssjssvg-s-podvypodvertom/ezhenedelnaya-podborka-krasivyx-effektov-na-csssvgjs-29.html

*Интерактивный барабан на SVG*
http://tympanus.net/codrops/2016/03/16/interactive-animated-svg-drum-kit/

*Материал от Frontender Magazine*
http://frontender.info/using-svg/

*Дмитрий Барановский про возможности SVG*
https://www.youtube.com/watch?v=SeLOt_BRAqc

**Демонстрация возможностей на SVG**

_Объединение возможностей SVG и CSS-переменных_<BR>
http://codepen.io/g12n/pen/JEYRLN

_Редактирование SVG в реальном времени_<BR>
http://codepen.io/osublake/pen/QdbQjN

**Онлайн-редактор векторной графики**

1. https://vectr.com

**Практика:**

1. Расположить текст вокруг надписи по кругу.

2. Наложить на текстовую надпись текстуру.

3. При наведении размывать картинку

4. Адаптивное лого






