---
description: Download the latest release of Monogatari
---

# Step 2: Download Monogatari

Once you've got your [environment set up](step-1-setup-your-environment.md), it's time to download Monogatari!

## Download Options

### 1. From the Website

The official website ([https://monogatari.io/](https://monogatari.io/)) provides the latest releases. You'll find options for:

- **Stable Release**: Recommended for most users
- **Nightly/Development**: Latest features, may have bugs

### 2. From GitHub

Visit the [Monogatari GitHub repository](https://github.com/Monogatari/Monogatari):

- **Main branch**: Latest stable release
- **Development branch**: Cutting-edge features (for version 2.0+)

To download from GitHub:
1. Go to the repository page
2. Click the green "Code" button
3. Select "Download ZIP"

### 3. From Release Announcements

Check the [Monogatari Forums](https://community.monogatari.io/t/news) for announcements on new releases with direct download links.

## Setting Up Your Download

### From Website or Release Announcements

1. Download the ZIP file
2. Extract/unzip the files using your preferred tool ([7-Zip](https://www.7-zip.org/) works great)
3. You're ready to go!

### From GitHub (Development Branch)

If you downloaded from the GitHub development branch:

1. Extract the ZIP file
2. Navigate to the `dist` folder inside
3. Copy the contents of `dist` to your project directory
4. You're ready to start!

## Verifying Your Download

After extraction, you should see a structure like this:

```
your-project/
├── assets/
│   ├── characters/
│   ├── images/
│   ├── music/
│   ├── scenes/
│   ├── sounds/
│   └── voices/
├── engine/
├── js/
│   ├── main.js
│   ├── options.js
│   ├── script.js
│   └── storage.js
├── style/
│   └── main.css
├── index.html
└── service-worker.js
```

## Next Steps

Once you have Monogatari downloaded and extracted, proceed to:

- [Step 3: Get Familiarized](step-3-get-familiarized.md) - Learn about the project structure
- [Step 4: Make Your First Visual Novel](step-4-make-your-first-visual-novel.md) - Start creating!
