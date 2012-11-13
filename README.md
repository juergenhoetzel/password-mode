password-mode
=============

Emacs minor mode to hide sensitive information in buffers (passwords)

Example Usage:

```lisp
(require 'password-mode)
(add-hook 'text-mode-hook 'password-mode)
```