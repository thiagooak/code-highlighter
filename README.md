# Code Highlighter

A simpler implementation of [syntax-highlight-element](https://github.com/andreruffert/syntax-highlight-element).

## Usage

Read-only
```html
<code-highlighter
    language="clojure"
    spellcheck="false"
    >(defn greet [name] (str "Hello, " name) )</code-highlighter>
```

Editable
```html
<code-highlighter
    language="clojure"
    contenteditable="plaintext-only"
    spellcheck="false"
    oninput="this.highlight()"
    >(defn greet [name] (str "Hello, " name) )</code-highlighter>
```

## Installation

### CDN

Add Prism core and the languages you want to enable

```html
  <script src="https://cdn.jsdelivr.net/npm/prismjs@1.30.0/components/prism-core.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/prismjs@1.30.0/components/prism-clojure.min.js"></script>
```

Add Code Highlighter
```html
<script type="module"
        src="https://cdn.jsdelivr.net/npm/@thiago.oak/code-highlighter@latest/code-highlighter.js"></script>
```

Add Code Highlighter theme
```html
<link rel="stylesheet"
      href="https://cdn.jsdelivr.net/npm/@thiago.oak/code-highlighter@latest/prettylights.css"/>
```
