# company-solidity

## Overview
This is a simple company-mode back-end for autocompletion for the Solidity programming langauge. It is intended to be used with [solidity-mode](https://github.com/ethereum/emacs-solidity).

### What it does
Give completion suggestions for solidity keywords, global variables, and address methods.

### What it isn't
In a word, smart. The completion suggestions are *not context dependent*.

### Something to watch out for
`company-mode` teats `.` as the end of a word, and will cut off compeletion suggestions when you type a `.`. So, when you've typed `msg` you will get `msg.sender`, `msg.value` etc. as completion suggestions. However, as soon as you type `msg.`, the suggestions will disappear.

## Installation

First, install the package from MELPA with `M-x package-install RET company-solidity RET`, then put the following in your `init.el`:

```lisp
(require 'company-solidity)
```

Alternatively, to install with [use-package](https://github.com/jwiegley/use-package), put the following in your `init.el`:

```lisp
(use-package company-solidity
  :ensure t
  :after (company))
```

That's it. Now open up a file in `solitidy-mode` and try it out!

## Usage

Completion suggestions from the `company-solidity` back-end will automatically appear when `solidity-mode` is your `major-mode`.

## Local Variables

If you want autocomplete suggestions to include local variables, as well as Solidity keywords, add the following to your `init.el`:

```lisp
(add-hook 'solidity-mode-hook
	(lambda ()
	(set (make-local-variable 'company-backends)
		(append '((company-solidity company-capf company-dabbrev-code))
			company-backends))))
```
