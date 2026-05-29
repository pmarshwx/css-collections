# markdown-css

CSS stylesheets for branding documents (and, in time, websites) with
**Oklahoma Baptist University** colors.

| Color     | Hex       |
| --------- | --------- |
| OBU Green | `#295b30` |
| OBU Gold  | `#c48b2b` |

## Stylesheets

### `obu.css`

Styles Markdown previews and Markdown→PDF exports with OBU branding. Designed
for the VS Code *Markdown PDF* / *Markdown Preview* extensions and *Marked 2*.

It targets the `body`, `.vscode-body`, and `.markdown-body` containers those
tools use, and includes an `@media print` block tuned for PDF output.

**Usage (VS Code Markdown PDF):** add the absolute path to your settings —

```jsonc
{
  "markdown-pdf.styles": ["/Users/pmarshwx/Documents/backups/markdown-css/obu.css"]
}
```

**Usage (Marked 2):** Preferences → Style → add `obu.css` as a custom style.

#### Worksheet helper classes

`obu.css` also provides classes for printable worksheets:

| Class            | Purpose                                              |
| ---------------- | ---------------------------------------------------- |
| `.qa-block`      | Keeps a question + its answer area on the same page  |
| `.answer-space`  | Blank fixed-height answer area                       |
| `.answer-lines`  | Ruled (lined) answer area                            |
| `.answer-box`    | Bordered answer box                                  |
| `.page-break`    | Forces a page break in PDF output                    |

## Reference / preview

[`examples/sample.md`](examples/sample.md) exercises every style and helper
class in `obu.css` (headings, callouts, definition lists, multiple-choice
`.choices`, task lists, `mark`/`kbd`, code, tables, and the `qa-block` answer
areas). Preview it with `obu.css` applied to see the full look, and use it as a
visual check after editing the stylesheet.

## Issue tracking

Work is tracked with [beads](https://github.com/gastownhall/beads) (`bd`).
Run `bd ready` to see available work, or `bd list` for everything.

## License

Personal/internal use.
