# Трансформации

Cвойство transform модифицирует объект и его положение

http://www.w3schools.com/cssref/css3_pr_transform.asp<BR>  (пробуем оранжевую кнопку play it)

```css
transform:rotate(45deg); // повернет блок на 45 градусов
```

Сейчас свойство transform работает во всех современных браузерах, но для обеспечения работы в более ранних версих необходимо ставить префикс. Запись, указанная выше обеспечивает работу как в ранних версиях, так и в поздних.

```css
div {
-ms-transform:rotate(7deg);/* IE 9 */
-webkit-transform:rotate(7deg);/* Chrome, Safari, Opera */
transform:rotate(7deg);
}
```

Перемещаем объект на 100 пикселей вправо, на 200 пикселей вниз

```css
transform:translate(100px,200px);  
```

Увеличиваем объект в два раза по горизонтали, в три раза по вертикали
```css
transform: scale(2,3);  
```

 Деформирует наш блок
```css
transform: skew(20deg,10deg); 
```

Если нам необходимо применить несколько трансформаций к объекту, это можно сделать через пробел. Например,

```css
transform: scale(2,3) skew(20deg,10deg);
```

**Изменение центра вращения**

Иногда нам нужно задать вращение(или другую трансформацию) не относительно центра объекта, а, например, вокруг его левого верхнего угла. В этом случае нам на помощь приходит свойство 

**transform-origin** 

transform-origin позволяет задавать координаты центра вращения. По умолчанию объект вращается относительно своего геометрического центра. transform-origin в этом случае установлен в занчение 50% 50%

```css
transform-origin:50% 50%;
```

```css
transform-origin: 0px 0px;
transform:rotate(30deg)
```
В данном примере вращение объекта проходит относительно левого угла.

Центр вращения можно вынести даже за пределы объекта.

```css
transform-origin: -50% -50%;
transform:rotate(30deg)
```
В данном случае проценты считаются от размеров объекта.

Большое количество примеров по данному свойству
http://theory.phphtml.net/css/transform-origin.html

**3D-трансформации**

Для вращения по другим осям нам необходимо использовать rotateX, rotateY, rotateZ

rotateY - вращает элемент по вертикальной оси
rotateX - вращает элемент по горизонтальной оси
rotateZ - ось Z направлена к нам, поэтому вращение по ней больше всего напоминает обычное вращение через rotate.

transform-style

```css
transform-style:preserve-3d;
```

backface-visibility - определяет будет ли видна задняя сторона объекта при его повороте.

```css
backface-visibility: hidden;
```



_Учебник по 3D-трансформациям_
http://desandro.github.io/3dtransforms/

**Перспектива**

Если мы хотим, чтобы при вращении прямоугольник искажался, как будто он "уходит в даль" нам необходимо добавить перспективу.

Картинки по теме
http://stackoverflow.com/questions/27684607/css-3-rotatey-and-rotatex-not-working-as-expected

```css
.parent {
    perspective: 1000px;
}

.child {
    transform: rotateY(50deg);
}
```

_Создание 3D-карусели_
http://desandro.github.io/3dtransforms/docs/carousel.html

**transition** 

transition позволяет добавить плавность в изменение свойств.

Например 

```css
div {
    width:200px;
    height:200px;
    background:lime;
    transition:transform 2s;
}

div:hover {
	transform:rotate(45deg)
}
```

Добавит нам плавность в повороте при наведении курсора

В случае, если нам нужно задать transition для нескольких свойств это делается через запятую

```css
transition: width 2s,height 2s;
```

Можно сделать, чтобы все свойства объекта изменялись плавно. Минус такого подхода, что при активных изменениях свойств блока браузер может начать потреблять очень много ресурсов компьютера, и Ваш сайт будет тормозить.

```css
transition: all 4s
```

Нужно понимать, что transition не будет давать плавность для свойств, у которых нет промежуточных значений.


Мы можем настраивать дополнительные свойства у transition


**transition-timing-function** - определяет как именно будет проходить анимация.

По умолчанию у нас значение ease - ускорение на старте и замедление в конце

```css
transition-timing-function: ease;
```

Можно сделать изменения линейными

```css
transition-timing-function:linear;
```


**transition-delay** - задает начальную задержку

```css
transition-delay: 1s;
```

Объединяя трансформации и transition можно получить очень интересные эффекты


**Полезное чтиво:**

1. Примеры hover-эффектов
http://tympanus.net/Tutorials/OriginalHoverEffects/index7.html<BR>
http://habrahabr.ru/post/149324/<BR>
http://www.webmasters.by/images/articles/css/circle-hover-effects/index6.html

2. Паралакс на чистом CSS
http://habrahabr.ru/post/235531/<BR>
http://keithclark.co.uk/articles/pure-css-parallax-websites/demo3/<BR>

3. Видео создания паралакса на чистом CSS
https://www.youtube.com/watch?v=ln5BWnYMSQA

4. 3D-фигуры
http://frontender.info/balls/   шары<BR>
http://learnsome.co/blog/zelda/ треугольники<BR>
http://habrahabr.ru/post/151300/ куб<BR>

5. Пример верстки
http://shinydemos.com/

**Практика:**

1.	При наведении мыши на элемент применяем к нему один из эффектов
2.	При наведении мыши блок плавно расширяется
3.	При наведении блок должен увеличиваться в размерах и менять цвет
4.	Есть три кнопки и блок. При наведении на кнопку у нас применяется один из эффектов
5.	Есть картинка. При наведении она вращается по часовой стрелке и уменьшается
6.	Создаем эффект вращения относительно внешнего центра
7. Имитируем эффект вращающейся монетки из Super Mario https://www.youtube.com/watch?v=OSkVb4MZ1Sw

8.     Есть интерфейс для выбора цвета из предыдущих разделов. Сделать, чтобы при наведении курсора на цветной блок, серый блок моментально менял цвет, но в дальнейшем удерживал этот цвет(даже если курсор за пределами интерфейса), пока курсор не соприкоснется с новым цветным блоком![](pics/13_advanced_css_selectors/rgb_blocks.gif)
9. Делаем один из эффектов для http://www.webmasters.by/images/articles/css/circle-hover-effects/index6.html	
10. Сделать, чтобы картинка появлялась снизу экрана при наведении курсора.
11. Сделать анимацию кнопки при наведении https://codepen.io/chriscoyier/pen/zrGvaq





