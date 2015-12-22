# Настройки шрифта

color – задает цвет шрифта. В отличии от остальных свойств идет без слова font
font-size:10px;  - размер шрифта
font-weight:normal;
                    bold;   //жирный
font-style: normal; 
                  italic;  //курсив
font-family:'Times New Roman', Times, Serif
font-family - выбирает гарнитуру шрифта. Наш сайт, может загрузиться на различных операционных системах и платформах (Windows, Linux, Mac), и там может не оказаться нашего шрифта. Поэтому создаем список шрифтов. Если мы оказались на Mac'e - там вряд ли есть Times New Roman (шрифты с пробелами указываем в кавычках), но там есть похожий шрифт Times.

В конце списка шрифтов мы можем задать семейство шрифтов. Если мы хотим использовать шрифт с засечками, то лучше применить семейство Serif. Шрифтам без засечек соответствует семейство Sans-serif
Web safe fonts – подборка шрифтов, которые доступны на большинстве компьютеров

http://www.cssfontstack.com/
http://www.w3schools.com/cssref/css_websafe_fonts.asp

Подключение внешних шрифтов
@font-face {
    font-family: myFirstFont;   
//название, под которым мы будем использовать данный шрифт
    src: url(sansation_light.woff); //адрес файла шрифта
}
В дальнейшем мы можем подключать шрифт к любому блоку через font-family: myFirstFont
Практика: скачиваем шрифт Lobster с http://webfont.ru/ и подгружаем его

Можно использовать библиотеку шрифтов от Google https://www.google.com/fonts
<link href='https://fonts.googleapis.com/css?family=Oswald' rel='stylesheet' type='text/css'>

Сервис Font-Squirell  http://www.fontsquirrel.com/  - генерирует все необходимые форматы шрифтов. Можно убрать лишние символы и таким образом обжать размер шрифта.

Задача: подключить Lobster к шрифту
Задача найти символьный шрифт и вывести сердце по центру экрана, например Zocial.
