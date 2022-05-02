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

}

/*
 * Ontion 1: simple icons
 */

@include svgaricons(
  (
    xxx1: 'path/to/svg',
    xxx_2: 'path/to/svg',
    xxx_3: 'path/to/svg',
  )
);

/*
 * Ontion 2: icons with variants (size, color)
 */
@include svgaricons(
  (/* ... */),
  (
    sizes: (10, 16, 32, 48, 64),
    colors: ('primary', 'secondary', 'success'),
  )
);

```

- Use the icons (ex.: `index.html`):

```html

<!-- Default -->
<i class="icon xxx1"></i>
<i class="icon xxx_2"></i>
<i class="icon xxx_3"></i>

<!-- Size variants -->
<i class="icon xxx1 size-48"></i>

<!-- Color variants -->
<i class="icon xxx1 color-primary"></i>

<!-- Hovered (different color) -->
<i class="icon xxx1 hovered-color-secondary"></i>
<i class="icon xxx1 color-primary hovered-color-success"></i>

<!-- Hovered (different source) -->
<i class="icon xxx1 hovered-icon-zzz"></i>

```

## Options

Pass options using the third parameter.

```scss
@include svgaricons(
  (/* ... */),
  (/* ... */),
  (
    var_prefix: 'app',
    naming: (
      icon: 'i', // .icon -> .i; .icon-xxx -> .i-xxx
      size: 's', // .icon-size-32 -> .i-s-32
      color: 'c', // .icon-xxx-color-primary -> .i-xxx-c-primary
      hovered: 'h', // .icon-hovered-color-success -> .i-h-c-success
    )
  )
);
```

## License

**@lamnhan/svgaricons** is released under the [MIT](https://github.com/lamnhan/svgaricons/blob/master/LICENSE) license.
