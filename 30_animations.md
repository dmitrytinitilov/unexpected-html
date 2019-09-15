# Анимации

Для работы в ранних версиях Chrome, может использоваться префикс  -webkit

Например:
@-webkit-keyframes  и –webkit-animation

```css
@keyframes example{
    0%   {background-color:red;}
    50%  {background-color:yellow;}
    100% {background-color:green;}
}
```

Элемент, к которому применяется анимация 

```css
div{
    width:100px;
    height:100px;
    background-color:red;
    animation-name:example;
    animation-duration:4s;
}
```

Вариант, когда состояний всего два

```css
@keyframes example {
    from {background-color: red;}
    to {background-color: yellow;}
}
```

**animation-name** - имя анимации

```css
animation-name:example;
```
**animation-duration** - продолжительность анимации

```css
animation-duration:4s;
```

**animation-delay** - стартовая задержка

```css
animation-delay:2s;  
```

**animation-iteration-count** -количество повторений

```css
animation-iteration-count:infinite;  
```
В данном случае бесконечное количество раз


**animation-direction** - в каком порядке будет проходить анимация

normal - значение по умолчанию. Анимация проходит в обычном направлении.

reverse - в обратном направлении

alternate - в прямом и обратном

```css
animation-direction:alternate;
```

**animation-timing-function** - свойство, которое позволяет задать как именно будет проходить анимация

*linear* - анимация будет проходить линейно<BR>
*ease*   - с ускорением и торможением<BR>
*ease-in* - медленный старт и ускорение<BR>

```css
animation-timing-function:linear;
```

**animation-fill-mode** - определяет, на какой набор свойств останется, после того как анимация была завершена

*none* - объект возвращается к своим исходным свойствам без свойств из анимации

*forwards* - объект остается со свойствами последнего кадра

*backwards* - объект остается со свойствами первого кадра.

**animation-play-state**

имеет два значения running и paused

```css
animation-play-state:running;
```

можно использовать, когда при наведении на элемент будет запускаться анимация

https://developer.mozilla.org/en-US/docs/Web/CSS/animation-play-state

Пример с применением задержек и продолжительностей
https://css-tricks.com/starting-css-animations-mid-way/

**Пошаговая анимация**
```css
animation: typing 4s steps(11) forwards
```

О пошаговой анимации
https://designmodo.com/steps-css-animations/


**Мультианимации**

```css
-webkit-animation: shrink 2s ease-out, pulsate 4s 2s infinite ease-in-out;
```

**Сокращенная запись**

```css
div {
   animation:example 5s linear 2s infinite alternate;
}
```

**Подборки анимаций в интерфейсах**

http://motion-ui.tumblr.com/
https://uimovement.com/
http://ui-animations.tumblr.com/


**Примеры мобильных анимаций**

http://thedesigninspiration.com/articles/20-incredible-mobile-ui-animations-in-gifs/

https://dribbble.com/samuelcouto/buckets/75737-Cool-UI-animations

https://dribbble.com/shots/1489493-Movie-app-Pull-down

https://dribbble.com/shots/1468679-Move-Product


**Полезное чтиво:**

1. Веб-анимации: где, зачем и почему?  
https://habrahabr.ru/company/ruvds/blog/321822/

2. Хорошая статья по свойствам анимации с примерами https://html5book.ru/css3-animation/

3. О timing functions в анимациях и transitions
https://habrahabr.ru/post/220715/

4. Подборка задач по анимации
https://codepen.io/jorgecardoso/post/1-css-transitions-and-animations

5. 10-ть принципов создания Web-анимаций
https://spark.ru/startup/webest/blog/18621/10-printsipov-sozdaniya-plavnoj-veb-animatsii

6. Подробное рассмотрение анимаций в CSS
https://habrahabr.ru/post/220715/

7. Примеры многокадровых анимаций
https://css-tricks.com/using-multi-step-animations-transitions/

8. Основные принципы использования анимации
https://vc.ru/design/46504-osnovnye-principy-ispolzovaniya-animacii-v-ux

9. Пример анимации с эхо-волнами
https://gist.github.com/AdonaiAraya/03a6a18c47bc4f2d9acf780e0c3f6b99

10. Glitch-эффект
https://ihatetomatoes.net/how-to-create-css-glitch-effect/

11. Применение SASS в анимации
https://hugogiraudel.com/2014/07/16/automating-css-animations-with-sass/



**Практика**
1.	Квадрат перемещается и меняет цвет.
2.	Сделать анимацию вращения планет
3.	Картинка вращается и уменьшается. Потом 
вращается в другую сторону и увеличивается.
4. Сделать так, чтобы квадрат сначала увеличивался по горизонтали, а потом начинал увеличиваться по вертикали.
5. Сделать анимацию иконки "входящий звонок"
6.	Сделать анимации с градиентом http://www.niekdekker.com/
7.	Сделать анимированный прогресс бар
8.	Сделать так, чтобы progress bar добавлялся делениями
9.	Спрайты








