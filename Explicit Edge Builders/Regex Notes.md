_Regex Notes_ allow you to leverage your existing note name structure. You can turn a note into a regex note by adding the following to your frontmatter:

```yaml
---
BC-regex-note-regex: "<regex>"
BC-regex-note-field: "<field>"
---
```

Where `<regex>` is a valid JavaScript regex (without the surrounding `/`), and `<field>` is one of your [[Edge Fields|edge fields]]. This will tell Breadcrumbs to find all notes that match the regex (using the **full path** of the note), and add edges from the regex note to the matches using the field you specify.

> [!NOTE]
> The `BC-regex-note-regex` value gets passed directly to the Javascript [RegExp](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp) constructor, so you can use that to troubleshoot your regex.

For example, find all notes with the word `psychology` in the path, and point `down` to them:

```yaml
---
BC-regex-note-field: "down"
BC-regex-note-regex: "psychology"
---
```

```mermaid
graph TB
	1(Regex Note.md) -->|down| 2(psychology/DSM 5.md) & 3(university/psychology course.md)
```

## `BC-regex-note-flags`

You can also add flags to the regex by adding the `BC-regex-note-flags` field to the frontmatter of the regex note.

```yaml
---
BC-regex-note-flags: "<flags>"
---
```

Where `<flags>` is a string of any combination of `g`, `i`, and `m` (for global, case-insensitive, and multi-line, respectively). e.g. `gim` would add all three flags.

> [!TIP]
> In practice, the most useful flag is `i`, to match case-insensitively.
> i.e. `BC-regex-note-flags: "i"`

## Settings

- **Default field**: Choose a fallback [[Edge Fields|field]] to use when only `BC-regex-note-regex` is present. This is useful if you have a _lot_ of regex notes, and don't want to add the `BC-regex-note-field` to each one.
