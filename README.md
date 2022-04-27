# SVG-ar-ICONS

Another way to use SVG icons. It's "SUGAR ICONS", baby!

## Install

```bash
npm i @lamnhan/svgaricons
```

## Usage

- Register icons (ex.: `_icons.scss`):

```scss
@import '@lamnhan/svgaricons';

/*
 * Define theme palettes
 * (use this tool for recoloring: https://angel-rs.github.io/css-color-filter-generator/)
 */

:root {

  // colors
  --color-primary: #3880ff;
  --color-secondary: #eb445a;
  --color-success: #2dd36f;

  // recolors
  --recolor-primary: brightness(0) saturate(100%) invert(37%) sepia(73%) saturate(1013%) hue-rotate(193deg) brightness(106%) contrast(104%);
  --recolor-secondary: brightness(0) saturate(100%) invert(45%) sepia(84%) saturate(2892%) hue-rotate(324deg) brightness(91%) contrast(102%);
  --recolor-success: brightness(0) saturate(100%) invert(90%) sepia(90%) saturate(2470%) hue-rotate(65deg) brightness(90%) contrast(82%);

  // gradients
  --gradient-primary: linear-gradient(45deg, darken(#13abdb,5%), #B10DC9);
  --gradient-secondary: linear-gradient(80deg, orange, darken(darkred,2%));
  --gradient-success: linear-gradient(180deg, #28d6e4, #04f44f);
}

/*
 * Ontion 1: simple icons
 */

@include svgaricons(
  (
    icon1: 'path/to/svg',
    icon_2: 'path/to/svg',
    'icon-3': 'path/to/svg',
  )
);

/*
 * Ontion 2: icons with size variants
 */
@include svgaricons(
  (/* ... */),
  (
    sizes: (10, 16, 32, 48, 64)
  )
);

/*
 * Ontion 4: icons with color/gradient variants
 */
@include svgaricons(
  (/* ... */),
  (
    /* var_prefix: 'app', */
    colors: ('primary', 'secondary', 'success'),
    gradients: ('primary', 'secondary', 'success'),
  )
);

/*
 * Ontion 3: icons with both size and color/gradient variants
 */
@include svgaricons(
  (/* ... */),
  (
    sizes: (10, 16, 32, 48, 64),
    colors: ('primary', 'secondary', 'success'),
    gradients: ('primary', 'secondary', 'success'),
  )
);

```

- Use the icons (ex.: `index.html`):

```html

<!-- Default -->
<i class="icon icon-icon1"></i>
<i class="icon icon-icon_2"></i>
<i class="icon icon-icon-3"></i>

<!-- Size variants -->

<!-- Color variants -->

<!-- Gradient variants -->

```

## License

**@lamnhan/svgaricons** is released under the [MIT](https://github.com/lamnhan/svgaricons/blob/master/LICENSE) license.
