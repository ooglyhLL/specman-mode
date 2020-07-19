==============================
Specman Editing Mode for Emacs
==============================

Overview
========

This Emacs mode is for editing source code written in the Specman/*e*
(aka IEEE1647) hardware verification language, as well as Specman
command files.

Notable features:

* Syntax highlighting

* Indentation

* Imenu

* GNU Global support via ggtags (https://github.com/leoliu/ggtags)

* Eldoc

* Comment editing in dedicated mode (derived from text-mode)

* Automatic header generation and insertion

* Uses Emacs’ syntax parsing facilities for traversing source
  code. This has a significant impact on ``specman-mode``’s code size
  as well as performance of e.g. indentation.


Installation
============

At the moment specman-mode consists of only one file. Download and put
it where Emacs can find it. See the documentation for the Emacs
variable ``load-path``. Then add something like the following to your
init file (e.g. ``$HOME/.emacs.d/init.el``)::

  (autoload 'specman-mode "specman-mode" "Specman code editing mode" t)
  (add-to-list 'auto-mode-alist '("\\.e\\(?:3\\|com\\|tst\\)?\\'" . specman-mode))
  (add-to-list 'auto-mode-alist '("\\.load\\'" . specman-mode))


Compatibility
=============

Historically, specman-mode used to work in both Emacs and XEmacs
(possibly SXEmacs, too). Development for the latter two projects has
slowed down a lot, while at the same time the pace of Emacs
development increased quite a bit.

``specman-mode`` has started to rely on Emacs’s syntax parsing
facilities which so far have only been partially ported to XEmacs,
yet. In particular the ``syntax-table`` text property is currently
only available in Emacs, as well as the syntax class “generic comment
delimiter” which is used to delimit space between code segments.
