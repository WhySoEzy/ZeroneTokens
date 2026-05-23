# Zerone library variables

This folder introduces the design variables for Zerone library. The variables are exported in both CSS custom properties and SCSS variable formats, so they can be used in plain CSS, Webflow custom code, Sass/SCSS projects, or as a reference when building UI systems.

## Figma Community

- 2.0 Official: [Get now](https://www.figma.com/community/file/1420604836785710311/the-q-library-2-0)
- 2.0 Lite: [Get now](https://www.figma.com/community/file/1501123476616291541/the-q-library-2-0-lite)

## Files

```txt
Zerone library variables
|-- css
|   |-- app.css
|   |-- color.css
|   |-- effect.css
|   |-- number.css
|   `-- typography.css
|-- scss
|   |-- app.scss
|   |-- color.scss
|   |-- effect.scss
|   |-- number.scss
|   `-- typography.scss
`-- README.md
```

- `css/app.css`: Entry file that imports all CSS variable files in the correct order.
- `scss/app.scss`: Entry file that imports all SCSS variable files in the correct order.
- `css/color.css`: CSS custom properties for color aliases, light/dark theme tokens, and support/status colors.
- `scss/color.scss`: SCSS variable version of `color.css`.
- `css/effect.css`: CSS custom properties for shadow/effect tokens. This file depends on color tokens.
- `scss/effect.scss`: SCSS variable version of `effect.css`. This file depends on color tokens.
- `css/number.css`: CSS custom properties for number, radius, and spacing tokens.
- `scss/number.scss`: SCSS variable version of `number.css`.
- `css/typography.css`: CSS custom properties for font family, font size, font weight, line height, and letter spacing tokens.
- `scss/typography.scss`: SCSS variable version of `typography.css`.

## CSS Usage

Use the `.css` files when you want native CSS variables:

```css
@import "./css/app.css";

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
@use "./scss/app" as *;
```

If your build setup uses older Sass imports, you can also import them directly:

```scss
@import "./scss/app";
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
- `effect` depends on `color`, so the entry files import `color` before `effect`.
- `typography` depends on `number`, so the entry files import `number` before `typography`.
- Dark theme aliases use the `-dark-` naming pattern, such as `$bg-dark-base-primary`, `$text-dark-base-primary`, and `$support-dark-error-primary`.
- Number tokens use `rem` values for scalable spacing and sizing.


