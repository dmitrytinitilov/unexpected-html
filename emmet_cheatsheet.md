# Emmet

Плагин Emmet к Sublime позволяет очень серьезно экономить время на генерации html

Для начала Вам понадобится Package Control. Нажимаете Ctrl+Shift+P, выбираете Install Package Control

После установки Package Control'a нажимаете еще раз Ctrl+Shift+P и выбираете пункт Package Control Install Packages. В появившемся окне вбиваете Emmet.

Для проверки установился ли Emmet, создайте пустой index.html файл, наберите в нем ! и сразу же нажмите tab. Должна появиться следующая заготовка

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
</head>
<body>
	
</body>
</html>
```

Теперь попробуем применить базовые конструкции Emmet'a

Набираем **.wrapper** и нажимаем tab. Должны получить следующую конструкцию
```html
<div class="wrapper"></div>
```

Если нам нужен тег отличный от div, то делаем

```
img.great
```

Преобразуется в 

```html
<img class="great">
```

Если нам нужно, чтобы какая-то конструкция повторялась то используем конструкцию *

**.block*4** после нажатия tab'a преобразуется в
```html
<div class="block"></div>
<div class="block"></div>
<div class="block"></div>
<div class="block"></div>
```
Если мы хотим, чтобы один блок шёл за другим, то используем +
**.block+.other_block** нажимаем tab, получаем

```html
<div class="block"></div>
<div class="other_block"></div>
```

Когда нам нужен один блок в другом применяем > . Например

**.outer>.inner** преобразуется в

```html
<div class="outer">
    <div class="inner">
    </div>
</div>
```

Мы можем комбинировать конструкции и использовать () для каких-либо выражений из них. Если нам нужно применять классы к div'ам, мы можем не писать div. Например

**.outer>(.orange+.violet)*4** преобразуется в 

```html
<div class="outer">
	<div class="orange"></div>
	<div class="violet"></div>
	<div class="orange"></div>
	<div class="violet"></div>
	<div class="orange"></div>
	<div class="violet"></div>
	<div class="orange"></div>
	<div class="violet"></div>
</div>
```

**Нумерация через $**

.block$*4 преобразуется в 

```html
<div class="block1"></div>
<div class="block2"></div>
<div class="block3"></div>
<div class="block4"></div>
```

**Вложенный текст**

div{Текст внутри}

```html
<div>Текст внутри</div>
```

**Вложенный текст с повторениями**

div.block${блок$}*4

```html
<div class="block1">блок1</div>
<div class="block2">блок2</div>
<div class="block3">блок3</div>
<div class="block4">блок4</div>
```

**Выход на уровень вверх**

Когда мы использовали значок > для вложенности, бывает нужно подняться на уровень вверх. Для этого используется ^

```
.outer>(.inner1+.inner2)+outer2
```

Без использования поднятия на уровень вверх мы получим

```html
<div class="outer">
    <div class="inner1">
    </div>
    <div class="inner2">
    </div>
    <div class="outer2">
    </div>
</div>
```

Поэтому заменим конструкцию на

```
.outer>(.inner1+.inner2)^outer2
```


```html
<div class="outer">
    <div class="inner1">
    </div>
    <div class="inner2">
    </div>
</div>
<div class="outer2">
</div>
```

**Практика:**

1. Сгенерируйте блок, внутри которого будет еще три блока
2. Используя Emmet сгенерируйте шахматную доску размером 7 на 7. Удалять из кода можно не более одной ячейки


