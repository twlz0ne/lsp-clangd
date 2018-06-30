# lsp-clangd

A configuration for an Emacs LSP client for Clang-based languages
using [`clangd`](https://clang.llvm.org/extra/clangd.html) as the
language server.

## Requirements

* [`clangd`](https://clang.llvm.org/extra/clangd.html)
* [`lsp-mode`](https://github.com/emacs-lsp/lsp-mode)

## Installing `clangd`

Since `clangd` is part of `clang-tools-extra` since Clang 5, it can be
installed by all the same methods for installing Clang 5 or later.

With macOS, the easiest way is to install via Homebrew.

``` shell
brew install llvm
```

## Enabling `lsp-clangd`

Currently, the only way to install `lsp-clangd` is to download it from
https://github.com/emacs-lsp/lsp-clangd.git and configure it yourself.
MELPA support, which will greatly simplify enabling `lsp-clangd` is
coming soon.

### Using `use-package`

``` emacs-lisp
(use-package lsp-clangd
  :load-path
  "<path-to-lsp-clangd>"
  :init
  (add-hook 'c-mode--hook #'lsp-clangd-c-enable)
  (add-hook 'c++-mode-hook #'lsp-clangd-c++-enable)
  (add-hook 'objc-mode-hook #'lsp-clangd-objc-enable))
```

### Manually

Install `lsp-mode` via some suitable method and clone this repository
to a suitable path, *e.g.* `<path-to-lsp-clangd>`.

```emacs-lisp
(add-to-list 'load-path "<path-to-lsp-clangd>")

(require 'lsp-clangd)

(add-hook 'c-mode--hook #'lsp-clangd-c-enable)
(add-hook 'c++-mode-hook #'lsp-clangd-c++-enable)
(add-hook 'objc-mode-hook #'lsp-clangd-objc-enable)
```
