password-mode
=============

An Emacs minor mode to hide sensitive information in buffers (passwords)
using overlays.

Warning
-------

This is not a replacement for a real password manager. Emacs already provides
an implementation of the Secret Service API (Gnome Keyring client): secrets.el

But there may be situation when you have to deal with passwords in plain text files.
You can further increase security by using GPG: http://blog.bogosity.se/2011/01/12/managing-passwords-using-gnupg-git-and-emacs/



Example Usage
-------------

```lisp
(require 'password-mode)
(add-hook 'text-mode-hook 'password-mode)
```

How are passwords recognized?
-----------------------------

There is a prefix regexp used to find the text before the password:

```lisp
(defcustom password-mode-password-prefix-regexs
  '("Password:\s+" "Passwort:\s+"))
```

There is also a regexp used to find the actual password:

```lisp
(defcustom password-mode-password-regex
  "\\([[:graph:]]*\\)"
```

How can I change passwords?
---------------------------

When you try to changes a password (hidden by the overlay) an Emacs
password prompt is invoked to read the actual password.