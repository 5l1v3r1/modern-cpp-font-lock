[![License GPL 3](https://img.shields.io/badge/license-GPL_3-green.svg)](http://www.gnu.org/licenses/gpl-3.0.txt)
[![MELPA](http://melpa.org/packages/modern-cpp-font-lock-badge.svg)](http://melpa.org/#/modern-cpp-font-lock)

# Modern C++ font-lock for Emacs #

Syntax coloring support for "Modern C++" - until C++17 and TS (Technical Specification). It is recommended to use it in addition with the `c++-mode` major-mode.

## Preview ##

Soon.

## Installation ##

### Melpa ###

`modern-cpp-font-lock` is available on the major `package.el` community maintained repo - [MELPA](http://melpa.org).

You can install it with the following command:

<kbd>M-x</kbd> `package-install` <kbd>[RET]</kbd> `modern-cpp-font-lock` <kbd>[RET]</kbd>

### Manual ###

#### Global setup ####

Download `modern-cpp-font-lock.el` into a directory of your [load-path][load-path]. Place the following lines in a suitable init file:

    (require 'modern-cpp-font-lock)
    (modern-c++-font-lock-global-mode t)

`modern-c++-font-lock-mode` will be activated for buffers using the `c++-mode` major-mode.

#### Local ####

For the current buffer, the minor-mode can be turned on/off via the command:

<kbd>M-x</kbd> `modern-c++-font-lock-mode` <kbd>[RET]</kbd>

## Configuration ##

You can modify the following lists to recognize more words or set it to `nil` to partially disable font locking:

 * `modern-c++-types` - list of C++ types
 * `modern-c++-hash-preprocessors` - list of C++ preprocessor words starting with `#`
 * `modern-c++-_preprocessors` - list of C++ preprocessor words starting with `_`
 * `modern-c++-__preprocessors__` - list of C++ preprocessor words surounded with `__`
 * `modern-c++-__preprocessors` - list of C++ preprocessor words starting with `__`
 * `modern-c++-keywords` - list of C++ keywords
 * `modern-c++-attributes` - list of C++ attributes
 * `modern-c++-operators` - list of C++ operators

### Example: Enable font-lock for more operators ###

By default, operators are no font locked (to avoid the _christmas tree_ effect). However, you could argue they can be overloaded and it could make sense to highlight all/some of them. It is a perfect example to show you how to customize this minor-mode:

With `c++-mode` and `modern-c++-font-lock-mode` enabled, you will see by default:

![See img/all-operator-off-sample.png for screenshot](./img/all-operator-off-sample.png)

Add `(add-to-list 'modern-c++-operators "=")` in your init file to enable extra font locking for operators. Now, `=` is highlighted:

![See img/all-operator-on-sample.png for screenshot](./img/all-operator-on-sample.png)

### Example: Disable font-lock for attributes  ###

You do not like some part of the font-locking? Fair enough. Let's disable the syntax highlighting for C++ attributes.

With `c++-mode` and `modern-c++-font-lock-mode` enabled, you will see by default:

![See img/attributes-on.png for screenshot](./img/attributes-on.png)

Add `(setq modern-c++-attributes nil)` in your init file to disable font locking for C++ attributes. Now, `[[maybe_unused]]` is no more highlighted:

![See img/attributes-off.png for screenshot](./img/attributes-off.png)

### More customization! ###

With the two previous examples, you can entirely re-define the font locking. Behind the scene of each variable, it's simply a list of strings. You can set it to `nil` and then add your own keywords.

## Mode line ##

When `modern-c++-font-lock-mode` is activated, `mc++fl` is displayed.

![See img/mode-line.png for screenshot](./img/mode-line.png)

## Feedback ##

Do not hesitate to ask questions or share suggestions - the package is fairly new.

Happy coding! :skull:

[Lud](http://lud.cc)

[load-path]: https://www.gnu.org/software/emacs/manual/html_node/emacs/Lisp-Libraries.html
