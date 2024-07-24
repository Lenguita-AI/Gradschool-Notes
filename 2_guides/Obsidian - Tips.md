Most if not all of these will come directly from the Obsidian official documentation: https://help.obsidian.md/

## Aliases

f you want to reference a file using different names, consider adding _aliases_ to the note. An alias is an alternative name for a note.

Use aliases for things like acronyms, nicknames, or to refer to a note in a different language.

### Add an alias to a note

To add an alias for a note, add `aliases` property in the note [Properties](https://help.obsidian.md/Editing+and+formatting/Properties). Aliases should always be formatted as a list in YAML.

```md
---
aliases:
  - Doggo
  - Woofer
  - Yapper
---

# Dog
```

### Link to a note using an alias

To link to a note using an alias:

1. Start typing the alias in an [internal link](https://help.obsidian.md/Linking+notes+and+files/Internal+links). Any alias shows up in the list of suggestions, with a curved arrow icon next to it.
2. Press `Enter` to select the alias.

Obsidian creates the link with the alias as its custom display text, for example `[[Artificial Intelligence|AI]]`.

Note

Rather than just using the alias as the link destination (`[[AI]]`), Obsidian uses the `[[Artificial Intelligence|AI]]` link format to ensure interoperability with other applications using the Wikilink format.

### Find unlinked mentions for an alias

By using [Backlinks](https://help.obsidian.md/Plugins/Backlinks), you can find unlinked mentions of aliases.

For example, after setting "AI" as an alias for "Artificial intelligence", you can see mentions of "AI" in other notes.

If you link an unlinked mention to an alias, Obsidian turns the mention into an [internal link](https://help.obsidian.md/Linking+notes+and+files/Internal+links) with the alias as its display text.

## Embedding

### Embed a note in another note

To embed a note:

```md
![[Internal links]]
```

You can also embed links to [headings](https://help.obsidian.md/Linking+notes+and+files/Internal+links#Link to a heading in a note) and [blocks](https://help.obsidian.md/Linking+notes+and+files/Internal+links#Link to a block in a note).

```md
![[Internal links#^b15695]]
```

The text below is an example of an embedded block:

Learn how to link to notes, attachments, and other files from your notes, using _internal links_. By linking notes, you can create a network of knowledge.

### Embed an image in a note

To embed an image:

```md
![[Engelbart.jpg]]
```

![Engelbart.jpg > outline](https://publish-01.obsidian.md/access/f786db9fac45774fa4f0d8112e232d67/Attachments/Engelbart.jpg)

You can change the image dimensions, by adding `|640x480` to the link destination, where 640 is the width and 480 is the height.

```md
![[Engelbart.jpg|100x145]]
```

If you only specify the width, the image scales according to its original aspect ratio. For example, `![[Engelbart.jpg|100]]`.

![Engelbart.jpg#outline](https://publish-01.obsidian.md/access/f786db9fac45774fa4f0d8112e232d67/Attachments/Engelbart.jpg)

You can also embed an externally hosted image by using a markdown link. You can control the width and height the same way as a wikilink.

```md
![250](https://publish-01.obsidian.md/access/f786db9fac45774fa4f0d8112e232d67/Attachments/Engelbart.jpg)
```

![250](https://publish-01.obsidian.md/access/f786db9fac45774fa4f0d8112e232d67/Attachments/Engelbart.jpg)

### Embed an audio file in a note

To embed an audio file:

```md
![[Excerpt from Mother of All Demos (1968).ogg]]
```

### Embed a PDF in a note

To embed a PDF:

```md
![[Document.pdf]]
```

You can also open a specific page in the PDF, by adding `#page=N` to the link destination, where `N` is the number of the page:

```md
![[Document.pdf#page=3]]
```

You can also specify the height in pixels for the embedded PDF viewer, by adding `#height=[number]` to the link. For example:

```md
![[Document.pdf#height=400]]
```

### Embed a list in a note

To embed a list from a different note, first add a [block identifier](https://help.obsidian.md/Linking+notes+and+files/Internal+links#Link to a block in a note) to your list:

```md

- list item 1
- list item 2

^my-list-id
```

Then link to the list using the block identifier:

```md
![[My note#^my-list-id]]
```

### Embed search results

To embed search results in a note, add a `query` code block:

````
```query
embed OR search
```
````

For example:

Note

[Obsidian Publish](https://help.obsidian.md/Obsidian+Publish/Introduction+to+Obsidian+Publish) doesn't support embedded search results. To see the example, open Obsidian Help locally inside Obsidian.

```query
embed OR search
```

## Tags

Add a tag to a note

To create a tag, enter a hash symbol (`#`) in the editor, followed by a keyword. For example, `#meeting`.

You can also add tags using the `tags` [property](https://help.obsidian.md/Editing+and+formatting/Properties). Tags in YAML should always be formatted as a list:

```yaml
---
tags:
  - recipe
  - cooking
---
```

### Find notes using tags

To find notes using the [Search](https://help.obsidian.md/Plugins/Search) plugin, use the `tag` [search operator](https://help.obsidian.md/Plugins/Search#Search operators) in your search term, for example `tag:#meeting`.

You can also search for tags by clicking on them in your notes.

To find notes using the [Tags view](https://help.obsidian.md/Plugins/Tags+view) plugin, select **Tags: Show tags** in the [Command palette](https://help.obsidian.md/Plugins/Command+palette), and then select the tag you want to search for.

### Nested tags

Nested tags define tag hierarchies that make it easier to find and filter related tags.

Create nested tags by using forward slashes (`/`) in the tag name, for example `#inbox/to-read` and `#inbox/processing`.

Both the [Search](https://help.obsidian.md/Plugins/Search) and [Tags view](https://help.obsidian.md/Plugins/Tags+view) plugins support nested tags.

### Tag format

You can use any of the following characters in your tags:

- Alphabetical letters
- Numbers
- Underscore (`_`)
- Hyphen (`-`)
- Forward slash (`/`) for [Nested tags](https://help.obsidian.md/Editing+and+formatting/Tags#Nested tags)

Tags must contain at least one non-numerical character. For example, #1984 isn't a valid tag, but [y1984](https://publish.obsidian.md/#y1984) is.

Tags are case-insensitive. For example, [tag](https://publish.obsidian.md/#tag) and [TAG](https://publish.obsidian.md/#TAG) will be treated as identical.

Note

Tags will display with the casing they are first created with in the [Tags view](https://help.obsidian.md/Plugins/Tags+view).  
For example, creating [Tag](https://publish.obsidian.md/#Tag) and then [TAG](https://publish.obsidian.md/#TAG) will display [Tag](https://publish.obsidian.md/#Tag) for both.

Tags can't contain blank spaces. To separate two or more words, you can instead use the following formats:

- [camelCase](https://publish.obsidian.md/#camelCase)
- [PascalCase](https://publish.obsidian.md/#PascalCase)
- [snake_case](https://publish.obsidian.md/#snake_case)
- [kebab-case](https://publish.obsidian.md/#kebab-case)