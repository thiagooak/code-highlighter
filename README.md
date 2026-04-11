# <code-highlighter>

![npm](https://img.shields.io/npm/v/@thiago.oak/code-highlighter)
![jsDelivr](https://img.shields.io/jsdelivr/npm/hm/@thiago.oak/code-highlighter)
![license](https://img.shields.io/npm/l/@thiago.oak/code-highlighter)

A lightweight `<code-highlighter>` custom element that provides syntax highlighting without DOM mutation, using the CSS Custom Highlight API

[Demo](https://thiagooak.github.io/code-highlighter/example-cdn.html)

## Features

- No DOM mutation for highlighting (no `<span>` injection)
- Uses Prism.js's tokenizer, but lets you decide how to import it
- Works as a read-only viewer or simple editor
- Minimal, only [50 lines](./code-highlighter.js) of JavaScript

## Limitations

- Requires a modern browser with [CSS Custom Highlight API](https://developer.mozilla.org/en-US/docs/Web/API/CSS_Custom_Highlight_API) support
- Prism must be loaded before `<code-highlighter>` runs

## Usage

### Read-only

```html
<code-highlighter
  language="clojure"
  spellcheck="false"
>
(defn greet [name] (str "Hello, " name))
</code-highlighter>
```

### Simple Editor
```html
<code-highlighter
  language="clojure"
  contenteditable="plaintext-only"
  spellcheck="false"
  oninput="this.highlight()"
>
(defn greet [name] (str "Hello, " name))
</code-highlighter>
```

Note: Consider debouncing calls to highlight() to avoid re-tokenizing on every keystroke

## API

### `highlight()`

Recompute syntax highlighting

```html
<code-highlighter oninput="this.highlight()"></code-highlighter>
```

## Installation

1. Add [Prism](https://prismjs.com/) core and any languages you need

```html
  <script src="https://cdn.jsdelivr.net/npm/prismjs@1.30.0/components/prism-core.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/prismjs@1.30.0/components/prism-clojure.min.js"></script>
```

2. Add `<code-highlighter>`

```html
<script type="module"
        src="https://cdn.jsdelivr.net/npm/@thiago.oak/code-highlighter@latest/code-highlighter.js"></script>
```

3. Add a theme

```html
<link rel="stylesheet"
      href="https://cdn.jsdelivr.net/npm/@thiago.oak/code-highlighter@latest/prettylights.css"/>
```

## Styling

Highlight colors are defined with `::highlight()` selectors. Your [theme](./prettylights.css) sets them

## Credits

* Inspired by https://www.bram.us/2024/02/18/custom-highlight-api-for-syntax-highlighting/
* Similar to https://github.com/andreruffert/syntax-highlight-element
