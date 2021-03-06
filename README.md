# highlight.js Sytax highlighting for Stan

This repo contains a little bit of code to produce highlight.js support for the [Stan](http://mc-stan.org) probabilistic programming language.

`./stan_funcs.R` webscrapes the relevant `.tex` manual files from the [Stan GitHub repo](https://github.com/stan-dev/stan), and pulls out some of Stan's keywords, for adding to the template file (`./highlight-stan.template.js`). It writes the result to `./highlight.js/src/languages/stan.js`, in a forked git submodule of the highlight.js source.


![highlight.js syntax highlighting for Stan, (probabilistic programming language)](https://s3-us-west-2.amazonaws.com/brendan-misc/screenshot.png)

## Features
Highlighting for Stan's:

* Model blocks (`data`, `parameters`, `model`, etc.)
* Probability distributions (`normal`, `ordered_logistic`, `lkj_corr_cholesky`, etc.)
* Data storage and types (`matrix`, `vector`, `corr_matrix`, etc.)
* Keywords (`if`, `then`, `for`, etc.)
* Literals and numbers
* Comments

## Notes
`beta` and `gamma` have been removed from the list of probability distribution keywords, as they're commonly used as parameter-variable names in Stan code.

As Stan is not your usual programming language, some parts of it's syntax don't have styleable highlight.js classes, and some of the styleable highlight.js classes have no equivalent in Stan. So, many of the keywords are mapped to arbitrary classes, with the aim of it looking good. I used tomorrow night 80s as my reference, as that's what I tend to edit in.

## Pull Requests
I've submitted the code to support Stan as a [pull request](https://github.com/isagalaev/highlight.js/pull/1019) to the highlight.js maintainers. If you have any ideas about how to improve support (I'm sure more could be done with regexps), or you just have strong feelings about colours/classes, I'd be happy to accept a pull request (and propagate changes to the highlight.js PR).
