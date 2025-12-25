---
description: Install all the tools you need to create your visual novel
---

# Step 1: Setup Your Environment

To develop in Monogatari you'll need the same tools used for web development. This means all you need is a **text editor** for editing HTML, JavaScript, and CSS files. Optionally, you may also use a **local web server** while developing your novel.

## Getting a Browser

You already have one, but is it the best one for development?

We recommend using either **[Chrome](https://www.google.com/chrome/)** or **[Firefox](https://www.mozilla.org/en-US/firefox/)** for development. While your game will run in any modern browser, both Chrome and Firefox have excellent developer tools that will make debugging and testing much easier.

### Why These Browsers?

- Built-in developer console for debugging
- Network inspection for asset loading
- Performance profiling tools
- Service worker debugging support

## Getting a Code Editor

What editor to use comes down to personal preference, but almost any text/code editor should work—you can even use Windows Notepad! However, using a code editor designed for development will make your life much easier with features like:

- Syntax highlighting (colors for functions, variables, etc.)
- Code auto-completion
- Error detection
- Multiple file management

### Recommended Free Editors

1. **[Visual Studio Code](https://code.visualstudio.com/)** - Most popular, great extensions
2. **[Atom](https://atom.io/)** - Highly customizable
3. **[Brackets](http://brackets.io/)** - Great for web development

If you've never used a code editor before, we recommend **Visual Studio Code** for its ease of use and excellent JavaScript support.

## Getting a Local Web Server (Optional)

A web server retrieves and sends files to your browser when you visit a website. While optional, running a local web server enables important features during development.

### Features That Require a Web Server

| Feature | Why It Needs a Server |
| :--- | :--- |
| [Asset Preloading](../configuration-options/game-configuration/asset-preloading.md) | Uses service workers (requires HTTP/HTTPS) |
| Offline Support | Service worker caching |
| Save/Load with IndexedDB | Some browsers restrict file:// access |

### Simple Server Options

#### Option 1: VS Code Live Server Extension

If you're using Visual Studio Code:
1. Install the "Live Server" extension
2. Right-click `index.html` and select "Open with Live Server"

#### Option 2: Python (Built-in)

If you have Python installed:

```bash
# Python 3
python -m http.server 8000

# Python 2
python -m SimpleHTTPServer 8000
```

Then open `http://localhost:8000` in your browser.

#### Option 3: Node.js

If you have Node.js installed:

```bash
npx serve
```

#### Option 4: Web Server for Chrome

Install the [Web Server for Chrome](https://chrome.google.com/webstore/detail/web-server-for-chrome/ofhbbkphhbklhfoeikjpcbhemlocgigb) extension. This creates a simple server using Chrome—you can then access it from any browser.

## Verifying Your Setup

Once you have:
- ✅ A modern browser installed
- ✅ A code editor installed
- ✅ (Optional) A local web server ready

You're ready to [download Monogatari](getting-monogatari.md)!

## Next Steps

- [Step 2: Download Monogatari](getting-monogatari.md)
