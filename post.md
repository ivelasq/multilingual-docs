# Creating multilingual documentation with Quarto


During a recent [coffee chat with Wes McKinney and Hadley
Wickham](https://youtu.be/D-xmvFY_i7U), a participant mentioned:

> We want to use Quarto to share documentation with different contexts,
> same documentation, but quickly switching between R and Python for our
> users, that need to see one language or the other.

[Quarto](https://quarto.org/) is a multilingual authoring system by
Posit, and its built-in support for multiple languages makes it an
excellent choice for developers and educators looking to bridge this
gap. There are several options for those looking to provide
documentation in different languages.

## Group tabsets on a page

Quarto allows for
[tabsets](https://quarto.org/docs/output-formats/html-basics.html#tabsets)
that present different content in tabs.

You can create [grouped
tabsets]((https://quarto.org/docs/output-formats/html-basics.html#tabset-groups))
on a page and tabs within a group are all swtiched together. So, for
example, if you have R code chunks under an “R” tabset and your user
selects an R tab, then they all switch on the page.

Create a grouped tabs by defining a `group` in your div.

``` md
:::{.panel-tabset group="language"}
:::
```

Test it out below:

<div class="panel-tabset" group="language">

## R

``` r
1 + 1
```

## Python

``` python
1 + 1
```

</div>

Here is the second tabset:

<div class="panel-tabset" group="language">

## R

``` r
1 + 1
```

## Python

``` python
1 + 1
```

</div>

[See an grouped tab example here](grouped-tabsets.qmd).

## tabby extension
