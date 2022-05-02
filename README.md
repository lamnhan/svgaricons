# SVG-r-ICONS

Another way to use SVG icons with SCSS. It's "SUGAR ICONS", baby!

Demo: <https://svgricons.lamnhan.com>

## Install

```sh
npm i @lamnhan/svgricons
```

## Usage

- Step 1: Define theme palettes (ex.: `_variables.scss`)

(Use this tool for recoloring: https://angel-rs.github.io/css-color-filter-generator/)

```scss
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
```

- Step 2: Register icons (ex.: `_icons.scss`):

```scss
@import '@lamnhan/svgricons';

// Option 1: simple icons
@include svgricons(
  (
    xxx: 'path/to/svg',
    yyy: 'path/to/svg',
    zzz: 'path/to/svg',
  )
);

// Ontion 2: icons with custom sizes, colors
@include svgricons(
  (/* ... */),
  (
    sizes: (10, 16, 32, 48, 64),
    colors: ('primary', 'secondary', 'success'),
  )
);

```

- Step 3: Use the icons (ex.: `index.html`):

```html
<!-- Default -->
<i class="icon xxx"></i>
<i class="icon yyy"></i>
<i class="icon zzz"></i>

<!-- Size variants -->
<i class="icon xxx size-48"></i>

<!-- Color variants -->
<i class="icon xxx color-primary"></i>

<!-- Hovered (different color) -->
<i class="icon xxx hovered-secondary"></i>
<i class="icon xxx color-primary hovered-success"></i>

<!-- Hovered (different source) -->
<i class="icon xxx hovered-xxx2"></i>
```

## Options

You can pass along options using the third parameter.

```scss
@include svgricons(
  (/* ... */),
  (/* ... */),
  (
    // You this if variables have a prefix
    // ex.: --app-color-primary, --app-recolor-secondary
    var_prefix: 'app',
    // Naming the classes
    naming: (
      icon: 'i', // .icon -> .i
      size: 's', // .size-32 -> .s-32
      color: 'c', // .color-primary -> .c-primary
      hovered: 'h', // .hovered-success -> .h-success
    )
  )
);
```

## License

**@lamnhan/svgricons** is released under the [MIT](https://github.com/lamnhan/svgricons/blob/master/LICENSE) license.
