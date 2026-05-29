# Sample Handout — obu.css Style Reference

This document exercises every style defined in `obu.css`. Open it in your
Markdown previewer / PDF exporter with `obu.css` applied to see the full OBU
look in one place, and use it as a visual check after editing the stylesheet.

## Heading Hierarchy

### Level 3 — Topic

#### Level 4 — Subtopic

##### Level 5 — Detail

###### Level 6 — Label

Body text sits at 13px with a 1.4 line-height. **Bold**, *italic*, and
~~strikethrough~~ all work, as do [links](https://www.okbu.edu) styled in OBU
green with a gold underline. Highlight a key term with <mark>spaced
repetition</mark>, and show a shortcut like <kbd>Cmd</kbd> + <kbd>S</kbd>.

## Callouts

<div class="note">

Callouts are written as raw HTML `<div>` blocks. Leave a blank line after the
opening tag so Markdown inside still renders.

</div>

<div class="tip">

**Tip:** You can put any Markdown — lists, code, **bold** — inside a callout.

</div>

<div class="warning">

Common mistake: forgetting to convert units before plugging into the formula.

</div>

<div class="example">

If $f(x) = x^2$, then the average rate of change on `[1, 3]` is 4.

</div>

<div class="key-term">

**Derivative** — the instantaneous rate of change of a function.

</div>

<div class="note no-label">

This callout uses `class="note no-label"` to suppress the auto label.

</div>

## Definition List

Term
: A word or phrase being defined.

Hypothesis
: A testable, falsifiable prediction.

Variable
: A quantity that can change within an experiment.

## Lists

- Unordered item
- Another item
  - Nested item
- Third item

1. First ordered item
2. Second ordered item
3. Third ordered item

### Task / Checklist

- [x] Read chapter 4
- [ ] Complete problem set
- [ ] Review before quiz

## Code & Syntax Highlighting

Inline code looks like `print("hello")`. A fenced Python block:

```python
def factorial(n):
    # base case
    if n <= 1:
        return 1
    return n * factorial(n - 1)  # recursive step

print(factorial(5))  # 120
```

## Blockquote

> "Education is not the filling of a pail, but the lighting of a fire."
> — attributed to W. B. Yeats

## Table

| Concept      | Symbol | Example      |
| ------------ | :----: | ------------ |
| Sum          |   Σ    | Σ x_i        |
| Mean         |   x̄    | (Σ x_i) / n  |
| Probability  |  P(A)  | P(heads) = ½ |

---

## Quiz Section

### Multiple Choice

**1.** What is the derivative of $x^2$?

<div class="choices">

1. $x$
2. $2x$
3. $x^2 / 2$
4. $2$

</div>

### Short Answer

<div class="qa-block">

**2.** Define *photosynthesis* in one sentence.

<div class="answer-lines"></div>

</div>

<div class="qa-block">

**3.** Show your work for $\int_0^1 2x\, dx$.

<div class="answer-box"></div>

</div>

<div class="qa-block">

**4.** List three branches of government.

<div class="answer-space"></div>

</div>

<div class="page-break"></div>

## After the Page Break

Anything following a `<div class="page-break"></div>` starts on a new page in
the PDF export.
