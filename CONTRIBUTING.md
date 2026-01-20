# Contributing

Thank you for your interest in contributing to the tldraw Snippets Library! This guide explains how to add new diagram elements.

## What Contributions Are Welcome

- New diagram elements with working copy/paste snippets
- Bug fixes for broken snippets
- New categories (if they don't fit existing ones)

## Naming Conventions

### Folders

- Use **kebab-case** for folder names: `robustness-diagram`, `class-diagram`
- Keep names short but descriptive

### Files

- Image files: `element-name.svg` (kebab-case, lowercase)
- README files: Always `README.md` (uppercase)

### Examples

```
library/
  my-new-category/
    README.md
    my-element.svg
    my-element-dark.svg
    another-element.svg
    another-element-dark.svg
```

## Required Entry Format

Every element entry **must** follow this exact template:

````markdown
## Element Name

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./element-name-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="./element-name.svg">
  <img alt="Element Name" src="./element-name.svg">
</picture>

<details>
<summary>Copy/paste snippet</summary>

```html
<meta charset="utf-8"><div data-tldraw="">YOUR_SNIPPET_HERE</div>
```

</details>
````

**Note:** The `<picture>` element allows GitHub to automatically show the appropriate image based on the user's color scheme preference.

## How to Add a New Element

### Step 1: Create the Element in tldraw

1. Open [tldraw.com](https://tldraw.com)
2. Create your diagram element
3. Select the element(s)
4. Copy (Ctrl/Cmd + C)

### Step 2: Get the Snippet

1. Paste the copied content into a clipboard inspector like: [Clipboard Inspector](https://evercoder.github.io/clipboard-inspector/)
2. You'll see HTML like: `<meta charset="utf-8"><div data-tldraw="">...</div>`

### Step 3: Create the Preview Images (Light & Dark)

You must provide both light and dark versions of your element:

1. In tldraw, select your element
2. Right-click → "Export as" → Toogle transparent → SVG

### Step 4: Add to the Library

1. Navigate to the appropriate category folder (or create a new one)
2. Add your image file
3. Edit the category's `README.md`
4. Add your entry following the required format above
5. Add a horizontal rule (`---`) between entries

### Step 5: Submit

1. Fork this repository
2. Create a branch: `git checkout -b add-element-name`
3. Commit your changes: `git commit -m "feat: add element-name to category"`
4. Push and open a Pull Request

## Important Rules

### Snippet Formatting

- **DO NOT** reformat the JSON inside snippets
- **DO NOT** wrap long lines
- **DO NOT** pretty-print or indent the data
- **DO** keep snippets exactly as exported from tldraw

Snippets contain serialized tldraw data. Any modification may break the paste functionality.

### Images

- Use SVG format
- Keep file sizes reasonable (< 500KB)
- Ensure the element is clearly visible
- Use a transparent background
- **Always include both light and dark versions** (`element.svg` and `element-dark.svg`)

### Content Guidelines

- Only submit elements you have created or have rights to share
- Do not include copyrighted logos or proprietary content
- Keep elements generic and reusable

## Attribution

By contributing, you confirm that:

1. You created the diagram elements yourself, OR
2. You have permission to share them, AND
3. You agree to license your contribution under this project's license

## Questions?

Open an issue if you have questions about contributing or need help with the process.
