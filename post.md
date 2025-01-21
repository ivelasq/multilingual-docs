# Creating multilingual documentation with Quarto


During a recent [coffee chat with Wes McKinney and Hadley
Wickham](https://youtu.be/D-xmvFY_i7U), a participant shared an
interesting use case:

> We want to use Quarto to share documentation with different contexts,
> same documentation, but quickly switching between R and Python for our
> users, that need to see one language or the other.

[Quarto](https://quarto.org/) is a multilingual authoring system by
Posit, and its built-in support for multiple programming languages makes
it an excellent choice for developers, technical writers, and educators
looking to create flexible, multilingual documentation. Below, we’ll
explore two approaches to implement this functionality:

- [Group tabsets on a page](#groups)
- [Tabby extension](#tabby)

## Group tabsets on a page

Quarto’s
[tabsets](https://quarto.org/docs/output-formats/html-basics.html#tabsets)
allow you to organize content, such as R and Python code, in separate
tabs. Each heading in the tabset `div` will output a separate tab.

[Grouped
tabsets](https://quarto.org/docs/output-formats/html-basics.html#tabset-groups)
enable you to synchronize these tabs so that when a user switches to one
language, all related tabs on the page switch simultaneously.

Create grouped tabsets by assigning the same `group` attribute (e.g.,
`language`) to multiple tabset `div`s. Then, use headings to define each
tab, which will synchronize across the page. For example, selecting the
`R` tab below will switch all related tabs on the page to the tabs
containing R code.

```` md
:::{.panel-tabset group="language"}

## R

```r
R code here
```

## Python

```python
Python code here
```
:::

More stuff in between...

:::{.panel-tabset group="language"}

## R

```r
R code here
```

## Python

```python
Python code here
```
:::
````

(Insert link to example)

## tabby extension

The [Tabby extension](https://quarto.thecoatlessprofessor.com/tabby/) by
Coatless provides another way to create multilingual documentation.

Similar to the example above, you can assign a `group` attribute (e.g.,
`language`) a Tabby `div.` However, unlike grouped tabsets, where you
need to define the same headings across all tabsets for synchronization,
Tabby automatically creates tabsets for each code block in the Tabby
`div`. It will then synchronize tab switches across the document.

```` markdown
---
filters:
  - tabby
---

::: {.tabby group="language"}
```{r}
R code here
```

```{python}
Python code here
```
:::

More stuff in between...

::: {.tabby group="language"}
```{r}
R code here
```

```{python}
Python code here
```
:::
````

Additionally, Tabby lets you set a [default tab
selection](https://quarto.thecoatlessprofessor.com/tabby/#default-tab-selection),
which is handy if you would like to prioritize the most relevant
language for your audience.

(Insert link to example)

## Learn more

We are excited for you to present R and Python (or other languages) side
by side with Quarto!

- See grouped tabset examples in our [Posit
  Docs](https://docs.posit.co/licensing/licensing-faq.html#license-file-in-container).
- Search more Quarto extensions in the [Quarto extension
  gallery](https://m.canouil.dev/quarto-extensions/).
