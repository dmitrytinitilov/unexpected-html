# # Переменные в CSS

**Создание переменной:**

```css
:root {
  --block-color: violet;
}

#block {
  color: var(--block-color);
}
```

**Использование через функцию сalc()**

```css

:root {
  --sidebar_width:20;
}

.sidebar {
  width:calc(var(--sidebar_width) * 1%);
}
```

**Пример изменения CSS-переменных на лету**

http://codepen.io/dmitrytinitilov/pen/BpoGvw


**Полезное чтиво:**<BR>

1. Примеры использования css-переменных http://frontender.info/css-variables-why-should-you-care/

2. Использование переменных для hsl-цветов https://www.sarasoueidan.com/blog/hex-rgb-to-hsl/

3. Про взаимодействие CSS-переменных и JavaScript
http://www.ericponto.com/blog/2014/09/17/share-css-variables-with-javascript/

4. Пример изменения CSS переменных с помощью JavaScript
http://codepen.io/wesbos/pen/adQjoY

5. iOS checkbox на чистом CSS
http://codepen.io/perry_nt/pen/dWXEEp

6. Еще один пример<BR>
https://googlechrome.github.io/samples/css-custom-properties/index.html





