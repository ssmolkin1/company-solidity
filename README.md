# company-solidity

## Overview
This is a simple company-mode back-end for autocompletion for the Solidity programming langauge. It is intended to be used with [solidity-mode](https://github.com/ethereum/emacs-solidity).

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
