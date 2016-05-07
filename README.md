# markdown-it-front-matter

> Plugin for processing front matter for markdown-it markdown parser.

## Valid Front Matter

Essentially, valid front matter is a fenced code block:

  * Indicated by **three** or **more** dashes: `---`
  * Opening and closing fences must be the same number of *dash* characters
  * Opening fence must begin on the first line of the markdown string/file
  * Opening fence must not be indented

```yaml
---
valid-front-matter: true
---
```

> The example above uses YAML but YAML is not required
> (bring your own front matter parser)


## Example

  * Nothing is parsed or rendered inside the front matter block.
  * Any markup inside the block is passed to the required callback function.

```javascript
const md = require('markdown-it')()
  .use(require('markdown-it-front-matter'), function(fm) {
    console.log(fm)
  });

md.parse('---\ntitle: This is the Title\nyo\n---\n# test\n----\ntest');

// logs: `title: This is the Title`
```

Code heavily borrowed from [markdown-it-container](https://github.com/markdown-it/markdown-it-container)

Thank you:
[puzrin](https://github.com/puzrin)
[rlidwka](https://github.com/rlidwka)