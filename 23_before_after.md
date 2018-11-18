# До и после. Селекторы :before :after

Подборка before after
http://www.hongkiat.com/blog/pseudo-element-before-after/

http://www.smashingmagazine.com/2011/07/learning-to-use-the-before-and-after-pseudo-elements-in-css/

https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Counters

Примеры
https://codemyviews.com/blog/the-lowdown-on-before-and-after-in-css
http://www.bennadel.com/blog/2445-using-css-pseudo-elements-before-and-after.htm
Пример с кнопками
http://www.esecamalich.com/older/blog/before-&-after/
http://archie-goodwin.net/load/specializirovannye_blogi/webmaster/css_psevdo_ehlementy_before_i_after_na_praktike/24-1-0-407

Много примеров
https://css-tricks.com/pseudo-element-roundup/
http://habrahabr.ru/post/154319/

Кнопки с помощью псевдо-элементов
http://tympanus.net/codrops/2012/01/11/css-buttons-with-pseudo-elements/

Счетчики
https://css-tricks.com/almanac/properties/c/counter-increment/
https://css-tricks.com/numbering-in-style/



LI { list-style-type: none;
 }

OL { counter-reset: list; 
}

LI:before {
        counter-increment: list 2;
        content: counter(list) ". ";
}

///////////////////////////////////////


body {
  counter-reset: my-awesome-counter;
}
section {
  counter-increment: my-awesome-counter;
}
section:before {
  content: counter(my-awesome-counter);
}
//////////////////////////////
section:before {
  content: counter(my-awesome-counter, upper-roman);
}
//////////////////////////////

p.box {
   width: 300px;
   border: solid 1px white;
   padding: 20px;
}

p.box:before {
   content: "#";
   border: solid 1px white;
   padding: 2px;
   margin: 0 10px 0 0;
}

