# The Q-library variables

This folder contains the design variables for The Q-library. The variables are exported in both CSS custom properties and SCSS variable formats, so they can be used in plain CSS, Webflow custom code, Sass/SCSS projects, or as a reference when building UI systems.

## Figma Community

- Official 2.0: [the q library 2 0](https://www.figma.com/community/file/1420604836785710311/the-q-library-2-0)
- Lite 2.0: [the q library 2 0 lite](https://www.figma.com/community/file/1501123476616291541/the-q-library-2-0-lite)

## Files

- `color-effect.css`: CSS custom properties for color aliases, light/dark theme tokens, support/status colors, and effect tokens.
- `color-effect.scss`: SCSS variable version of `color-effect.css`.
- `number.css`: CSS custom properties for number, radius, and spacing tokens.
- `number.scss`: SCSS variable version of `number.css`.
- `typography.css`: CSS custom properties for font family, font size, font weight, line height, and letter spacing tokens.
- `typography.scss`: SCSS variable version of `typography.css`.

## CSS Usage

Use the `.css` files when you want native CSS variables:

```css
@import "./number.css";
@import "./color-effect.css";
@import "./typography.css";

.button {
  color: var(--text-base-primary);
  background-color: var(--bg-brand-primary);
  border-radius: var(--radius-component-button);
  font-size: var(--font-size-web-component-button-base);
}
```

## SCSS Usage

Use the `.scss` files when working inside a Sass/SCSS project:

```scss
@use "./number";
@use "./color-effect";
@use "./typography";
```

If your build setup uses older Sass imports, you can also import them directly:

```scss
@import "./number";
@import "./color-effect";
@import "./typography";
```

Then use the variables:

```scss
.button {
  color: $text-base-primary;
  background-color: $bg-brand-primary;
  border-radius: $radius-component-button;
  font-size: $font-size-web-component-button-base;
}
```

## Notes

- CSS files use `--token-name` and `var(--token-name)`.
- SCSS files use `$token-name` and direct variable references.
- Dark theme aliases use the `-dark-` naming pattern, such as `$bg-dark-base-primary`, `$text-dark-base-primary`, and `$support-dark-error-primary`.
- Number tokens are converted to `rem` values for scalable spacing and sizing.
