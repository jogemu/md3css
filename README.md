# md3css

Pure CSS Material 3 Design with flexible icon placement. Leverages recent CSS features, including nesting to reduce redundancy, dynamic light-dark schemes with a wide color gamut and pseudo-classes that became part of Baseline as recently as May 2024. Change the hue of the color scheme, add a font or place an icon with just one CSS variable. Using inheritance, multiple elements can be influenced while combining stylesheets, classes and inline style.

![Demo](https://gist.githubusercontent.com/jogemu/f0c63ab30f60218b31efb578acf4c81d/raw/md3css.svg)


Common buttons are `<button>` or `<a>` within a `<fieldset>`. Use the respective button type in lower case as class and specify the optional leading icon by setting the CSS variable `--icon: url('/path/to/file.svg')` or `url('data:image/svg+xml;utf8,<svg>...</svg>')`. Since the image is used as a mask, the color of the image does not have to match the color scheme.

```html
<fieldset>
  <button>Text button</button>
  <a class="filled" style="--icon: url('/path/to/file.svg');">Filled button</a>
</fieldset>
```

Inputs without a label are not styled, but an id is not necessary. Put the label text in a `<span>` such that `<label><input/><span/></label>`. The previously introduced variable describes the optional leading icon and `--icon2` the optional trailing icon. Several of these inputs can be grouped in a fieldset with the classes for `chips`, `segmented` buttons or `switches`. Inputs other than `radio`, `checkbox` or `button` are unexpected for these classes and might misbehave.

```html
<label><input/><span>Text field</span></label> <!-- or textarea or select -->
<label><input type="range"/><span>Slider</span></label>
<fieldset class="chips"><label><input type="checkbox"/><span>Chip</span></label></fieldset> <!-- or class="segmented" or class="switches" -->
```

In addition to cards, there are other HTML elements that, if best practices are followed, should already be designed correctly.

```html
<!-- Cards -->
<section class="cards">
  <article><h2>Title</h2><p>Lorem ipsum</p></article>
  <article><hgroup><h2>Title</h2><p>Subhead</p></hgroup><fieldset><button>OK</button></fieldset></article>
</section>

<!-- Dialogs -->
<dialog><h2>Title</h2><p>Lorem ipsum</p><fieldset><button>OK</button></fieldset></dialog>

<!-- Top app bars -->
<header><a style="--icon: url('/path/to/file.svg');">Icon button</a><h1>Top app bar</h1></header>

<!-- Navigation bar -->
<nav><ul>
  <li><a style="--icon: url('/path/to/file.svg');">Label</a></li></ul>
</nav>
```
