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

**Полезное чтиво:**

1. Применение @supports на примере shape-outside и background-blend-mode  
  https://frontender.info/supports-will-change-your-life/ 