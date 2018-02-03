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

*MELPA pull request is pending. For now, you will need to install manually per the instructions below.*

First, clone the repo:

```bash
git clone https://github.com/ssmolkin1/company-solidity.git
```

Optionally, byte-compile the `company-solidity.el` file for faster loading and usage.

Then add the following line to your `init.el` file.

```lisp
(load "/path/to/company-solidity")
```

That's it. Now open up a file in `solitidy-mode` and try it out!

## Usage

Completion suggestions from the `company-solidity` back-end will automatically appear when `solidity-mode` is your `major-mode`.

## Local Variables

If you want autocomplete suggestions to include local variables, as well as Solidity keywords, add the following to your `init.el`:

```lisp
(add-hook 'solidity-mode-hook
	(lambda ()
	(load "/path/to/company-solidity")
	(set (make-local-variable 'company-backends)
		(append '((company-solidity company-capf company-dabbrev-code))
			company-backends))))
```
