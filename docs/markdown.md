import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Markdown Formatting

Modrinth's text fields, including project bodies and version changelogs, use [GitHub Flavored Markdown](https://github.github.com/gfm).

As the full GFM spec is too large to read comfortably and [GitHub's formatting guide](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax) contains features not included in GFM, this page serves as a quick reference for what types of formatting can be used on Modrinth.

:::info Important
The displayed features may not reflect the actual style used on Modrinth.
:::

HTML also works in all Markdown fields. However, use of HTML tends to override default element styles used on Modrinth. For the sake of consistency, we therefore advise against using HTML elements, except when there is no Markdown equivalent (e.g., spoilers and YouTube iframes).

You can view the spoiler below to see more specifics on how our HTML rendering works.

<details>
<summary>Supported HTML features</summary>

A broad subset of HTML is supported. The [default XSS whitelist](https://github.com/leizongmin/js-xss/blob/master/dist/xss.js#L12) is used, and the following tags are also supported:
- `kbd`
- `iframe` (only from YouTube or Discord)
- `input`
- `map`
- `picture`
- `source`

Additionally, certain elements also support being styled with the following CSS:
- `float`
- `image-rendering` (only the `pixelated` option, otherwise `auto` is used)
- `text-align`

</details>

## Basic formatting

<Tabs>
<TabItem value="source" label="Source">

```markdown
**Bold**
*Italic*
***Bold and Italic***
~~Strikethrough~~
```

</TabItem>
<TabItem value="preview" label="Preview">

**Bold**  
*Italic*  
***Bold and Italic***  
~~Strikethrough~~

</TabItem>
</Tabs>

## Code blocks

<Tabs>
<TabItem value="source" label="Source">

````markdown
`single-line code block`

```
multi
line
code
block
```
````

</TabItem>
<TabItem value="preview" label="Preview">

`single-line code block`

```
multi
line
code
block
```

</TabItem>
</Tabs>

:::tip
You can add a language (e.g. `java`) after the first three backticks to add code highlighting to the code block.
:::

## Block quotes

<Tabs>
<TabItem value="source" label="Source">

```markdown
> Some Quote
> > Nested Quote
```

</TabItem>
<TabItem value="preview" label="Preview">

> Some Quote
> > Nested Quote

</TabItem>
</Tabs>

## Links

<Tabs>
<TabItem value="source" label="Source">

```markdown
https://modrinth.com
[Embedded link](https://modrinth.com)
[Embedded link with title](https://modrinth.com 'Title')
[Reusable link]

<!-- (end of document) -->
[Reusable link]: https://modrinth.com
```

</TabItem>
<TabItem value="preview" label="Preview">

https://modrinth.com  
[Embedded link](https://modrinth.com)  
[Embedded link with title](https://modrinth.com 'Title')  
[Reusable link]

[Reusable link]: https://modrinth.com

</TabItem>
</Tabs>

:::note
All links have the following `rel` set by default: `noopener nofollow ugc`. If you don't know what this means, you probably don't need to worry about it.
:::

## Images

<Tabs>
<TabItem value="source" label="Source">

```markdown
![REPLACE ME WITH YOUR ALT TEXT](https://cdn.modrinth.com/modrinth-new.png)
![REPLACE ME WITH YOUR ALT TEXT](https://cdn.modrinth.com/landing-new/landing.webp 'REPLACE ME WITH AN OPTIONAL TITLE')
<!-- Use the Gallery tab on your project for image hosting! -->
```

</TabItem>
<TabItem value="preview" label="Preview">

![REPLACE ME WITH YOUR ALT TEXT](https://cdn.modrinth.com/modrinth-new.png)
![REPLACE ME WITH YOUR ALT TEXT](https://cdn.modrinth.com/landing-new/landing.webp 'REPLACE ME WITH AN OPTIONAL TITLE')

</TabItem>
</Tabs>

:::warning
[Alt text](https://accessibility.huit.harvard.edu/describe-content-images) is very important to use. Your project may be rejected if you don't add alt text! Refer to section 2.1 of [Modrinth's content rules](https://modrinth.com/legal/rules#general-expectations).
:::

## Headings

<Tabs>
<TabItem value="source" label="Source">

```markdown
# H1 Header
## H2 Header
### H3 Header
#### H4 Header
##### H5 Header
###### H6 Header
```

</TabItem>
<TabItem value="preview" label="Preview">
<strong>
<div style={{fontSize: 48}}>H1 Header</div>
<div style={{fontSize: 24}}>H2 Header</div>
<div style={{fontSize: 20}}>H3 Header</div>
<div style={{fontSize: 16}}>H4 Header</div>
<div style={{fontSize: 14}}>H5 Header</div>
<div style={{fontSize: 13.6}}>H6 Header</div>
</strong>
</TabItem>
</Tabs>

:::caution
Do not overuse headers, but do not underuse them either! Headers are meant to delineate different sections of content in your description. Entire sentences should never be inside a header.
:::

## Lists

### Unordered Lists

<Tabs>
<TabItem value="source" label="Source">

```markdown
- Entry 1
- Entry 2
    - Entry 2.1
    - Entry 2.2
- Entry 3
```

</TabItem>
<TabItem value="preview" label="Preview">

- Entry 1
- Entry 2
    - Entry 2.1
    - Entry 2.2
- Entry 3

</TabItem>
</Tabs>

### Ordered Lists

<Tabs>
<TabItem value="source" label="Source">

```markdown
1. Entry 1
2. Entry 2
    1. Entry 2.1
    2. Entry 2.2
3. Entry 3
```

</TabItem>
<TabItem value="preview" label="Preview">

1. Entry 1
2. Entry 2
    1. Entry 2.1
    2. Entry 2.2
3. Entry 3

</TabItem>
</Tabs>

## Tables

<Tabs>
<TabItem value="source" label="Source">

```markdown
| Title 1             | Title 2               | Title 3              |
|---------------------|:---------------------:|---------------------:|
| Cell 1:1            | Cell 1:2              | Cell 1:3             |
| Cell 2:1            | Cell 2:2              | Cell 2:3             |
| Cell 3:1            | Cell 3:2              | Cell 3:3             |
| Left-aligned column | Center-aligned column | Right-aligned column |
```

</TabItem>
<TabItem value="preview" label="Preview">

| Title 1             | Title 2               | Title 3              |
|---------------------|:---------------------:|---------------------:|
| Cell 1:1            | Cell 1:2              | Cell 1:3             |
| Cell 2:1            | Cell 2:2              | Cell 2:3             |
| Cell 3:1            | Cell 3:2              | Cell 3:3             |
| Left-aligned column | Center-aligned column | Right-aligned column |

</TabItem>
</Tabs>

:::note
Note the colons used in the second line of the table to change the column alignment.
:::

## Details (spoilers)

<Tabs>
<TabItem value="source" label="Source">

```html
<details>
<summary>Click me!</summary>

You clicked me!

</details>
```

</TabItem>
<TabItem value="preview" label="Preview">
<details>
<summary>Click me!</summary>
You clicked me!
</details>
</TabItem>
</Tabs>

:::caution
Markdown only works properly in details tags if there is at least one empty line between HTML and Markdown content.
:::

## Newlines

<Tabs>
<TabItem value="source" label="Source">

```markdown
This sentence will have an empty line

between its two segments.

---

This sentence will all
go on one line.

---

This sentence will be\
split into two lines

---

This sentence will also be  <!-- there are two spaces after this line -->
split into two lines
```

</TabItem>
<TabItem value="preview" label="Preview">

This sentence will have an empty line

between its two segments.

---

This sentence will all
go on one line.

---

<!-- This is not the same as above because Redocusaurus linebreaks are different
     from the linebreaks made by markdown-it, the MD plugin knossos uses -->
This sentence will be  
split into two lines

---

This sentence will also be  
split into two lines

</TabItem>
</Tabs>

## YouTube iframes

To use a YouTube iframe, copy-paste the following into your description:

```html
<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/REPLACE_THIS_TEXT_HERE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
```

Then, replace the text that says `REPLACE_THIS_TEXT_HERE` with the 11-character code that follows `/watch?v=` in the YouTube video URL. For example, it should look something like `d1YBv2mWll0`. Remove any query parameters like `si=randomText` or `wmode=transparent`.
