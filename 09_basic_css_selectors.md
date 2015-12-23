# Внешний CSS. Базовые CSS-селекторы

Способы подключения CSS

1) атрибут style
```html
<div style="width:200px;height:100px;background-color:red">
</div>
```
Серьезный минус в том, что CSS и HTML не разделены
2) тег &lt;style&gt;
Применим оформление ко всем ссылкам в документе

```html
<style>
A {
	color:red; //сделаем все ссылки красными
}
</style>
```

3) внешний CSS-файл
В &lt;head&gt; нашего html файла пишем
```<link rel="stylesheet" type="text/css" href="theme.css">```

А в theme.css добавляем CSS-селекторы
Зададим размеры и фоновую картинку для всех div'ов на сайте
```css
div {
	width:200px;
	height:200px;
       background:url('odessa_at_night.jpg');
}
```
**Базовые CSS-селекторы**

1. Свойства применяемые к тегу
index.html
<span>Наш текст</span>
style.css
span {
	color:black;
}

2. Применение свойств к классу
index.html
<div class="red_block">
</div>
style.css
.red_block {
	background-color:red;
}

3. Применение свойств к id
index.html
<div id="footer">
</div>
style.css
#footer {
	width:100%;
}