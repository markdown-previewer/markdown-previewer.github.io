
# Markdown Previewer

A lightweight, browser-based **Markdown previewer** with live GitHub‑flavored Markdown rendering, syntax highlighting, themes, and export tools — all in a single static HTML file.

This repository hosts the **GitHub Pages site** for the  
[`markdown-previewer` organization](https://github.com/markdown-previewer).

Live app: **https://markdown-previewer.github.io/**

---

## ✨ Features

- **Live preview**
  - Edit Markdown on the left, see rendered HTML on the right in real time.

- **GitHub‑flavored Markdown (GFM)**
  - Tables
  - Task lists (`- [x]`, `- [ ]`)
  - Fenced code blocks (```js ``` etc.)
  - Blockquotes, lists, headings, links, images, etc.

- **Syntax highlighting**
  - Powered by [`highlight.js`](https://highlightjs.org/)
  - Language-aware highlighting when you specify the language after the backticks:
    ```markdown
    ```js
    console.log("Hello, world!");
    ```
    ```

- **Dark / Light theme**
  - Toggle button in the toolbar
  - Remembers your choice using `localStorage`
  - Respects system preference on first load

- **File operations**
  - **Open** local `.md`, `.markdown`, or `.txt` files
  - **Save** current content as `.md` (download)
  - **Autosave**: current text is stored in `localStorage` so you don’t lose work if you refresh

- **Export**
  - **Export HTML**: download the rendered HTML as a standalone file
  - **Export PDF**: uses the browser’s **Print → Save as PDF** functionality, with print-friendly styles

- **Zero build tooling**
  - Plain **HTML + CSS + JavaScript**
  - Uses CDN-hosted libraries:
    - [`marked`](https://github.com/markedjs/marked) for Markdown → HTML
    - [`DOMPurify`](https://github.com/cure53/DOMPurify) for safe HTML sanitization
    - [`highlight.js`](https://highlightjs.org/) for code highlighting

---

## 🧪 Live Demo

The app is deployed via GitHub Pages:

> **https://markdown-previewer.github.io/**

Open the link in any modern browser and start typing Markdown.

---

## 🧰 Getting Started Locally

You can run this app locally without any build tools.

### Option 1: Open the file directly

1. Clone the repo:
   ```bash
   git clone https://github.com/markdown-previewer/markdown-previewer.github.io.git
   cd markdown-previewer.github.io
   ```

2. Open `index.html` in your browser:
   - Double-click `index.html`, **or**
   - In your browser: **File → Open File…** and select `index.html`

Everything runs purely client-side.

### Option 2: Use a simple static server (optional)

If you prefer to run via `http://localhost`:

```bash
# Using Python 3
python -m http.server 8000
# then open: http://localhost:8000/
```

---

## ✏️ Quick Markdown Syntax Guide

You can use these examples directly in the previewer.

### Headings

```markdown
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
```

### Emphasis

```markdown
*Italic text* or _Italic text_
**Bold text** or __Bold text__
***Bold and italic*** or ___Bold and italic___
```

### Lists

**Unordered list:**
```markdown
- Item 1
- Item 2
  - Nested item 2.1
  - Nested item 2.2
```

**Ordered list:**
```markdown
1. First item
2. Second item
3. Third item
```

### Links and Images

```markdown
[Link text](https://example.com)

![Alt text for image](https://via.placeholder.com/150)
```

### Code

**Inline code:**
```markdown
Use the `code` syntax for inline code.
```

**Code block:**
```markdown
```js
function hello(name) {
  console.log(`Hello, ${name}!`);
}
```
```

### Blockquotes

```markdown
> This is a blockquote.
> It can span multiple lines.
```

### Tables (GFM)

```markdown
| Column A | Column B | Column C |
|---------:|:--------:|---------|
| right    | center   | left    |
| 1        | 2        | 3       |
```

### Task Lists (GFM)

```markdown
- [x] Completed task
- [ ] Incomplete task
- [ ] Another item
```

Paste any of the above into the left pane to see how the previewer renders it.

---

## 🧱 Project Structure

This repository is intentionally minimal:

```text
markdown-previewer.github.io/
└── index.html   # All HTML, CSS, and JS in a single file
```

- All logic is embedded in `index.html`.
- No bundlers, no frameworks, no build step.
- External libraries are loaded from CDNs.

---

## 🔧 Customization (high-level)

If you’d like to customize the app:

- **Styling**
  - Update the CSS inside the `<style>` block in `index.html`.
  - Color variables live under `:root` and `[data-theme="dark"]`.

- **Default content**
  - Change the initial Markdown text in the `initContent()` function in the JS section.

- **Behavior / Features**
  - The main behavior (rendering, theme toggle, file operations, exports) is implemented in inline `<script>` tags at the bottom of `index.html`.
  - You can:
    - Add buttons in the toolbar
    - Change how exports work
    - Swap highlight.js themes by changing the CSS link for `highlight.js` in the `<head>`.

---

## 🤝 Contributing

Contributions and suggestions are welcome.

### Typical workflow

1. **Fork** this repository.
2. Create a feature branch:
   ```bash
   git checkout -b feature/my-improvement
   ```
3. Make your changes and commit:
   ```bash
   git commit -m "Add my improvement"
   ```
4. Push the branch:
   ```bash
   git push origin feature/my-improvement
   ```
5. Open a **Pull Request** against `main` on this repo.

Please include:

- A brief description of the change
- Any UI screenshots, if applicable
- Steps to test your changes

---

## 📜 License

This project is licensed under the **GNU General Public License v3.0 (GPL-3.0)**.  

You may redistribute and/or modify this software under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful,  
but **without any warranty**; without even the implied warranty of  
**merchantability** or **fitness for a particular purpose**. See the  
[GNU General Public License](https://www.gnu.org/licenses/gpl-3.0.en.html) for more details.

See the [LICENSE](./LICENSE) file in this repository for the full text of the GPLv3 license.

---

## 📫 Feedback / Issues

If you encounter a bug, have a feature request, or want to discuss ideas:

- Open an **issue** in this repository:  
  https://github.com/markdown-previewer/markdown-previewer.github.io/issues

Happy writing in Markdown!
