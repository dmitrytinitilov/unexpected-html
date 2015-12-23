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
