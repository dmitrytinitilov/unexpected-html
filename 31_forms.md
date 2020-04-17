# Формы

Формы
&lt;form&gt; атрибут action определяет куда именно будут отправляться данные из формы, атрибут method определяет каким методом http-протокола будут отправлять данные (GET или POST)

```html

<form action="script.php" method="GET">
    <input type="text" name="login">
    <input type="password" name="password">
    <input type="submit" value="Залогиниться">
</form>
```

&lt;input&gt; Различные типы text, password, hidden, submit, radio, checkbox. 

В **hidden** полях мы можем хранить дополнительную информацию в форме
```html
<input type="hidden" name="x" value="x_value">
```
**radio button**

Для того, чтобы сделать обеспечить переключение между radio-кнопками нужно сделать их с одним и тем же name

```html
<input type="radio" name="sex" value="Male">
<input type="radio" name="sex" value="Female">
```

**checkbox**

Для выделения добавляем атрибут checked

```html
<input type="checkbox" checked>
```

**&lt;select&gt;&lt;option&gt;
**


Это классический выпадающий список. То, что обычно называют классический ComboBox.

```html
Что делать дома?
<select>
  <option value="sitcom">Посмотреть  сериал</option>
  <option value="book">Почитать книгу</option>
  <option value="site" selected>Сверстать сайт</option>
</select>
```

**Полезное чтиво:**

1. Стилизация radiobutton и checkbox
http://code.stephenmorley.org/html-and-css/styling-checkboxes-and-radio-buttons/
2. Пример радио-баттонов  
https://codepen.io/AngelaVelasquez/pen/Eypnq



**&lt;textarea&gt;**

Текстовая область. Идеально подходит, когда нам нужна не одна строчка текста, а хороший текстовый блок.

```html
<textarea>
Тут может быть несколько строчек текста внутри
</textarea>
```

Чтобы убрать синее свечение при выделении

```css
textarea {
  outline: none;
}
```
Убираем resize

```css
textarea {
  resize: none;
}
```

Добавляем принудительный перенос
```html
<textarea wrap="off" cols="30" rows="5"></textarea>
```

Подробнее
https://css-tricks.com/textarea-tricks/

**Тег &lt;legend&gt;**

**Тег &lt;label&gt;**

```html
<label for="male">Male</label>
<input type="radio" name="gender" id="male" value="male"><br>
```

**range**

```html
<input type="range">
```

```html
<input type="range" min="5" max="10" step="0.01">
```

метки-риски

```html
<input type="range" list="tickmarks">

<datalist id="tickmarks">
  <option value="0">
  <option value="10">
  <option value="20">
  <option value="30">
  <option value="40">
  <option value="50">
  <option value="60">
  <option value="70">
  <option value="80">
  <option value="90">
  <option value="100">
</datalist>
```

**Полезное чтиво:**

1. Подробнее о range https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/range

2. Стилизация range средствами css
https://css-tricks.com/styling-cross-browser-compatible-range-inputs-css/

3. Стилизация range средствами css и js 
https://css-tricks.com/custom-interactive-range-inputs/


**атрибут tabindex**

**Особенности работы с формами в HTML5**

*Новые html5 типы для input'ов*<BR>
http://htmlbook.ru/html5/forms


**required, autofocus, placeholder**

*placeholder* - подсказка внутри input'a

```html
<input type="text" placeholder="Ваше имя">
```

*required* - обязательное для ввода поле

```css
:required {
  background: red;
}
```

```html
<input type="name" name="fname" required>
```

*autofocus* - ставит фокус на поле при его загрузке

**Псевдоклассы полей ввода**

:empty - пустое поле  

:focus - поле, у которого есть фокус  

:required - оформление для обязательных полей  

:optional - в противоположность required, оформление для необязательных полей  

:valid - срабатывает, если данные соотвествуют типу поля ввода, например введении емейла в input type="email"  

:invalid - и соответственно, если данные не верны, срабатывает этот псевдокласс  

:disabled - оформление для заблокированных полей  

:checked - срабатывает для выбранного checkbox или radio-button

Более подробный список селекторов для форм описан здесь
http://webdesignerwall.com/tutorials/the-power-of-css-selectors-and-how-to-use-them

**contenteditable="true"**

Для того, чтобы сделать контент внутри блока редактируемым ставим html-атрибут contenteditable="true"

```html
  <div contenteditable="true"></div>
```

Имитация placeholder для contenteditable

```css
[placeholder]:empty:before {
   content: attr(placeholder);
   color: #555; 
}

[placeholder]:empty:focus:before {
   	content: "";
}
```

Внимание! Чтобы сработал :empty нужно, чтобы не было лишних пробелов между дивами


**Полезное чтиво:**

1. Про дизайн форм  
https://uxplanet.org/designing-more-efficient-forms-structure-inputs-labels-and-actions-e3a47007114f#.i2q4e4uzh
2. Дизайн форм для залогинивания  
https://uxplanet.org/designing-ux-login-form-and-process-8b17167ed5b9#.42uiuca2p
3. Коллекция эффектов для текстовых полей ввода  
https://tympanus.net/Development/TextInputEffects/
4. checkbox или переключатели что и когда лучше использовать  
https://vc.ru/design/51721-chekboks-ili-pereklyuchatel-chto-vybrat-ux-dizayneru-pri-sozdanii-form-vybora

5. Примеры плохих интерфейсов через формы
https://userinyerface.com/

**Практика: **

1. Сделать внутри поля ввода иконку поиска (лупа)
2. При получении инпутом фокуса, фон за инпутом должен размываться.
3. При выборе чекбокса "Я хочу получать спам" показываем картинку со смайликом.
4. Добиться, чтобы при переключении радио-баттона менялась картинка.
5. Когда выбраны все три чекбокса, показываем пользователю смайлик.
6. Сделать имитацию placeholder для DIV'a с атрибутом contenteditable
7. Сделать, чтобы при клике на input, placeholder перетекал наверх