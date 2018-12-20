# @supports

@supports позволяет определить, поддерживается ли данная фича браузером

```css
@supports (animation-name: test) {
    … /* specific CSS applied when animations are supported unprefixed */
    @keyframes { /* @supports being a CSS conditional group at-rule, it can includes other relevant at-rules */
      …
    }
}
```

**Variable fonts**

1. Демка возможностей
https://v-fonts.com/

2. Описание от Google
https://developers.google.com/web/fundamentals/design-and-ux/typography/variable-fonts/


**Полезное чтиво:**

1. Применение @supports на примере shape-outside и background-blend-mode  
  https://frontender.info/supports-will-change-your-life/ 