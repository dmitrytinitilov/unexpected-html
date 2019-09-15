# Цвета, картинки, CSS-переменные

**Способы задания цвета**

1)	**red,black,white;** - простые названия цветов на английском. Изначально в HTML их было всего 16, но с приходом CSS их количество возросло на несколько сотен.

Если Вас вдохновляют всякие необычные названия типа LightSalmon или MediumSeaGreen, Вы можете почерпнуть их из списка ниже.

_CSS colors_ 
https://www.w3schools.com/colors/colors_names.asp

2)	**rgb(255,255,0);** - цвет на компьютере делится на три компоненты - красную, зеленую и синюю (**R**ed, **G**reen, **B**lue - **RGB**). Каждая компонента может быть представлена значением от 0 до 255.

Соответственно функция rgb позволяет нам задать эти три компоненты. Например

```css
color:rgb(0,0,100);
```
сделает цвет темно-синим

3)	**rgba(100,100,100,0.5)** - в целом функция аналогична предыдущей, но содержит четвертым параметром полупрозрачность. 1 - полностью непрозрачный цвет, 0 - полностью прозрачный. Все дробные значения - что-то между.

4)	**#FF0000**

Как и в любой записи цвета для вывода на дисплей, цвет делится на три компоненты - красную, зеленую, синюю. Под каждую компоненту выделяется два символа.

\#BA DB AD
Red Green Blue

В шестнадцатиричной системе помимо цифр 0-9 добавляется еще шесть цифр.

A  = 10<BR>
B  = 11<BR>
C  = 12<BR>
D  = 13<BR>
E  = 14<BR>
F  = 15<BR>

1A=1*16+A = 16+10 =26

Попробуйте ответить на вопрос чему будет равно
А1
AD
DA
FF

Для того, чтобы пользоваться этими кодами необязательно переводить все в десятичную систему. Часто достаточно просто прикинуть какой цвет перед нами.

Определите следующие цвета:

\#000000
\#FFFFFF
\#FF0000
\#BBBBBB
\#DD092A
\#1BB11B


5) **#fff**. Мы можем сократить запись цветов если цифры в записи повторяются. Например #fff означает #FFFFFF , а #000 - #000000

6)	**transparent** – прозрачный. Блоки по умолчанию прозрачные, но иногда нам нужно "вернуть" цвет к прозрачному. В этом случае как нельзя кстати приходится значение transparent


**Web Safe Colors** - набор цветов, которые гарантированно нормально отображаются на всех устройствах. Подборка утратила свою актуальность так как везде, включая мобильные и холодильники экраны с подержкой 16,7 млн цветов.

**О функции color в CSS4**

https://colorme.io/

**Сервисы для работы с цветами**

1. Color Picker сервис полностью дублирующий выбор цвета в Photoshop'e + подбор совместимого.
http://colorpicker.com

2. Цветовое колесо(Color Wheel) от Paletton для подборки совместимых цветов
http://paletton.com/

3. Color Wheel от Adobe
https://color.adobe.com/ru/create/color-wheel/


**Плагины для Sublime**

1. ColorPicker. После установки нажмите Ctrl+Shift+C, чтобы открыть окно выбора цвета
https://packagecontrol.io/packages/ColorPicker

2. Color Highlighter
https://packagecontrol.io/packages/Color%20Highlighter


**Интересное чтиво:**

1. О воздействии желтого 
http://www.petrick.ru/yellow

2. 7 способов использования синего в цветах вашей фирмы https://spark.ru/startup/logo/blog/31143/7-sposobov-ispolzovaniya-sinego-v-tsvetah-vashej-firm

3. 5 способов использования красного в цветах вашей фирмы https://spark.ru/startup/logo/blog/31834/5-sposobov-ispolzovaniya-krasnogo-v-tsvetah-vashej-firmi

4. О цветовых схемах под реальный проект
https://refactoringui.com/previews/building-your-color-palette/

5. Подборка сервисов для выбора цвета
https://habr.com/company/ua-hosting/blog/275919/

6. Разбор проблем с выбором цвета  
https://medium.com/eightshapes-llc/color-in-design-systems-a1c80f65fa3#.1vb9nf2sc

7. Новые возможности для работы с цветом: функция color,CSS-переменные, mix-blend-mode
https://frontender.info/the-power-of-rgba/

8. mix-blend-mode 
https://css-tricks.com/almanac/properties/m/mix-blend-mode/

9. Выбор цветов для темной темы
https://vc.ru/design/52140-darkmode



**Форматы графических файлов**

**jpeg**

+ 12 млн
+ для фотографий

- сжатие с потерей качества
- нет полупрозрачности
- нет анимации
- не подходит для картинок с резкими границами
- шумы

**png**

+ сжатие без потери качества
+ 12 млн цветов
+ поддерживает полупрозрачность
 
- для фотографий занимает в два раза больше чем jpeg
- нет анимации

**gif**

+ поддерживает анимацию
+ сжатие без потери качества
+ поддерживает полупрозрачность
+ хорошее сжатие для картинок с малым количеством цветов

- максимальное количество цветов 256 


**svg**

+ векторный формат
+ подходит для иконок

**bpg**<BR>
https://habrahabr.ru/post/276033/<BR>
https://eek.ro/why-bpg-will-replace-gifs-and-not-only/

**web-p**<BR>
https://habrahabr.ru/company/io/blog/261651/
https://habrahabr.ru/post/275735/

**flif**
https://habrahabr.ru/post/278745/

**Полезное чтиво:**

1. Форматы изображений
https://htmlacademy.ru/blog/113-image-formats

2. 13 приемов по оптимизации картинок
https://vc.ru/seo/74892-13-priemov-optimizacii-izobrazheniy-kak-vyyti-v-top-poiska-po-kartinkam

**Сервисы для оптимизации графики**

https://squoosh.app/

https://kraken.io/web-interface

https://imageoptim.com/mac

http://getoptimage.com/

**Переменные в CSS**

С помощью CSS-переменных мы можем задать основные и дополнительные цвета в нашем проекте.

```css
:root {
  --primary-color: violet;
}

#block {
  color: var(--primary-color);
}
```

[Подробнее о CSS-переменных](31_css_variable.html)

**Полезное чтиво:**

1. Использование переменных для hsl-цветов https://www.sarasoueidan.com/blog/hex-rgb-to-hsl/

