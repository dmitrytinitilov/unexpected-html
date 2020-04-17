# Анимации

Мы уже рассмотрели с Вами трансформации через свойство transform. В купе с transition и псевдоклассами мы сумели добиться анимации по событию. Но что если нам нужна многошаговая или циклическая анимации? За это отвечают свойства animation.

Как и в кино для анимации нам нужны кадры. Они задаются конструкцией keyframes. Обратите внимание, что example - это свойство нашей анимации.

```css
@keyframes example{
    0%   {background-color:red;}
    50%  {background-color:yellow;}
    100% {background-color:green;}
}
```

Элемент, к которому применяется анимация. animation-name - имя анимации, которое мы берем из keyframes,а animation-duration - продолжительность этой анимации.

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

**Пример анимации левитации**

```css
.block {
  width:100px;
  height:100px;
  background-color:orangered;
}

@keyframes do-levitation {
  0% {
    transform: translate(0, 0);
  }
  100% {
    transform: translate(0, 0.5em);
  }
}

.levitate {
  animation: do-levitation 1.2s alternate ease-in-out infinite;
}
```

Для "левитации" применим класс levitate к нашему блоку

```html
<div class="block levitate">
</div>
```


**animation-delay** - стартовая задержка, перед началом анимации

```css
animation-delay:2s;  
```

**animation-iteration-count** - количество повторений анимации

Ставим целое число или infinite для бесконечного числа раз.

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

Если нам нужно подключить несколько анимаций, мы можем это сделать через запятую. Удобно при подключении библиотек с анимациями.

```css
animation: shrink 2s ease-out, pulsate 4s 2s infinite ease-in-out;
```

**Сокращенная запись**

```css
div {
   animation:example 5s linear 2s infinite alternate;
}
```

**Animate.css**

Мы можем пользоваться готовыми эффектами для анимации. Одна из них animate.css

https://daneden.github.io/animate.css/

Подключаем библиотеку и используем название анимации.

Подключение

```html
<head>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/3.7.2/animate.min.css">
</head>
```

Пример применения к элементу

```html
<div class="animated infinite bounce delay-2s">
  Example
</div>
```



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

10. Пример эффекта для стерео-очков
https://ihatetomatoes.net/how-to-create-css-glitch-effect/



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









