# A tribute to light-blue Emacs theme

... which Emacs 29.1 made obsolete.

![image](https://github.com/habamax/forget-me-not-theme/assets/234774/d0a4ddad-fc89-424d-8031-0f61dfcb2189)

## Installation

With Emacs 29.1+:

```emacs-lisp
(package-vc-install "https://github.com/habamax/forget-me-not-theme")
```

Or download `forget-me-not-theme.el` into your `custom-theme-directory`.

## Fork additions (Doom-style extensions)

This fork extends upstream with features inspired by
[doom-themes](https://github.com/doomemacs/themes).

### Palette as data

Upstream binds its colors inside a `let*` that downstream code can't see.
This fork mirrors that palette into a public alist plus helpers, the
equivalent of `doom-color` / `doom-ref`:

```emacs-lisp
(fmn-color 'blue)        ;; => "#002faf"
(fmn-color 'bg)          ;; => "#add8e6"
(fmn-ref   'keyword)     ;; => "#002faf"  (semantic alias)
(fmn-ref   'function)    ;; => "#af0000"

(fmn-with-colors (blue bg)
  (message "%s on %s" blue bg))
```

Semantic aliases in `fmn-semantic`: `keyword`, `string`, `constant`,
`function`, `variable`, `type`, `builtin`, `operator`, `number`,
`preprocessor`, `doc`, `error`, `warning`, `success`.

### Tree-sitter face coverage

- Emacs 29+ native `font-lock-*-face` gap fillers
  (`punctuation`, `misc-punctuation`, `operator`, `property-name`,
  `variable-use`, `regexp-grouping-construct`,
  `regexp-grouping-backslash`).  The faces already styled by upstream
  (bracket, delimiter, number, function-call, property-use, escape,
  regexp) are left untouched.
- Full `tree-sitter-hl-face:*` set for the legacy `emacs-tree-sitter`
  package.

### Package faces upstream doesn't ship

`solaire-mode`, `neotree`, `treemacs`, `dashboard`, `vterm` and `eat`
(ANSI palette), `posframe` / `vertico-posframe` / `which-key-posframe`
borders, `corfu-popupinfo`, `doom-modeline-bar`, and a `mode-line-flash`
face for visual-bell setups.

### Customisation knobs

| Variable             | Default | Effect                                              |
|----------------------|---------|-----------------------------------------------------|
| `fmn-enable-bold`    | `t`     | When `nil`, suppress bold weights in the additions. |
| `fmn-enable-italic`  | `t`     | When `nil`, suppress italic slants in the additions.|

## Other themes

- [wildcharm-theme][1]: dark/light themes with good contrast.
- [sandcastle-theme][2]: light mid(low) contrast theme.

[1]: https://github.com/habamax/wildcharm-theme
[2]: https://github.com/habamax/sandcastle-theme
