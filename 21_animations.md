# Анимации

Для работы в ранних версиях Chrome, может использоваться префикс  -webkit
@-webkit-keyframes  и –webkit-animation

@keyframes example {
    from {background-color: red;}
    to {background-color: yellow;}
}

/* The element to apply the animation to */
div {
    width: 100px;
    height: 100px;
    background-color: red;
    animation-name: example;
    animation-duration: 4s;
}
 Можно задавать кадры через проценты

@keyframes example {
    0%   {background-color: red;}
    25%  {background-color: yellow;}
    50%  {background-color: blue;}
    100% {background-color: green;}
}

/* The element to apply the animation to */
div {
    width: 100px;
    height: 100px;
    background-color: red;
    animation-name: example;
    animation-duration: 4s;
}


animation-name: example;
animation-duration: 4s;  //продолжительность
animation-delay: 2s;  //задержка

Количество повторений
animation-iteration-count: infinite;  //в данном случае бесконечно
animation-direction: alternate;
animation-timing-function: linear;

Мультианимации
-webkit-animation: shrink 2s ease-out, pulsate 4s 2s infinite ease-in-out;

div {
    animation: example 5s linear 2s infinite alternate;
}


Примеры анимаций

http://www.creativebloq.com/css3/animation-with-css3-712437

http://www.hongkiat.com/blog/creative-css-animations/










