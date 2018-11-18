# Расширенные CSS селекторы

**Х+Y**

Применяется к селектору Y, если он идет в коде сразу после X.

Для примера возьмём два блока с классами first и second

```css
.first {
    width:100px;
    height:100px;
    background:grey;
    display:inline-block;
}

.second {
    width:100px;
    height:100px;
    background:cornflowerblue;    
    display:inline-block;
}```

![два блока](pics/14_advanced_css_selectors/two_blocks.gif)

Добавим в CSS участок с селектором +

```css
.first + .second {
    border:10px solid black; 
}
```

тогда в следующем примере у блока с классом .second появится граница

```html
<div class="first">
</div>
<div class="second">
</div>
```

![Применяем селектор плюс](pics/14_advanced_css_selectors/adv_selector_plus.gif)

А вот если добавить хотя бы один блок посередине, то границы уже не будет

```html
<div class="first">
</div>
<div class="block_in_the_middle">
</div>
<div class="second">
</div>
```

![Селектор плюс и блок посередине](pics/14_advanced_css_selectors/block_in_the_middle.gif)

**Х ~ Y**

```css
.first ~ .second {
    border:10px solid black; 
}
```

Этот CSS-селектор очень похож на X + Y, однако, является менее строгим. Теперь если блок second находится в коде после блока first, то к нему применится граница.

В этом случае second будет с границей.

![Применяем селектор тильда ~](pics/14_advanced_css_selectors/adv_selector_plus.gif)

```html
<div class="first">
</div>
<div class="second">
</div>
```

Для селектора **~** блок **block\_in\_the\_middle** - не помеха

```html
<div class="first">
</div>
<div class="block_in_the_middle">
</div>
<div class="second">
</div>
```

![Применяем селектор тильда ~](pics/14_advanced_css_selectors/tilda_selector.gif)



_Селектор будет работать только для элементов с общим родителем!_



**Х&gt;Y**

```css
.parent>.child {
    border:10px dashed black;
}
```

Разница между стандартными Х Y и X &gt; Y состоит в том, что рассматриваемый CSS-селектор будет выбирать только непосредственные дочерние элементы. Рассмотрим следующий код.

```html
<div class="parent">
    <div class="child">
        <div class="child">
        </div>
    </div>
</div>
```

**.parent &gt; .child** применится к "внешнему" child'у, но не применится к внутреннему

**.parent .child** применится к двоим блокам класса child

**Практика:**

1. Есть четыре блока с одинаковым классом. При наведении на любой из этих блоков должен меняться цвет у последующего блока.
2. Есть блок. В нем два вложенных блока. Один из них скрыт. При наведении на внешний блок, видимый вложенный блок скрывается, невидимый – появляется.
3. При наведении на иконку меню, она преобразуется в полноценное меню. Пока курсор находится на меню - меню удерживается
4. Сделать, чтобы блок при нажатии увеличивался, менял цвет и держал свой размер, пока мы с него не переместимся

5. Три цветных блока и один серый под ними. При наведении на любой из цветных блоков, серый окрашивается в тот же цвет.  
   ![](pics/13_advanced_css_selectors/rgb_blocks.gif)

6. Есть галерея фотографий. При наведении на фотографию, показываем ее в большом блоке
7. Реализуем систему классов для "вложенных" комментариев \(пример [http://habrahabr.ru](http://habrahabr.ru)\)



