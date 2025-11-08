# ContextualSearch

<!-- Plugin description -->
**ContextualSearch** is a powerful JetBrains IDE plugin that enables instant web searches from selected text in your editor, terminal, or consoles. Configure multiple search engines and access them with a simple right-click.

## ✨ Features

### 🔍 Universal Text Search
- Search selected text from **code editor**, **terminal**, and **consoles**
- Right-click context menu integration
- Opens results in your default browser

### ⚙️ Customizable Search Engines
- Add unlimited search engines (Google, Stack Overflow, GitHub, MDN, etc.)
- Enable/disable engines individually
- Custom URL patterns with `%s` placeholder
- Import/Export configurations as JSON

### 🎨 User-Friendly Interface
- Intuitive settings panel in **Settings → Tools → ContextualSearch**
- Quick add, edit, and remove engines
- Double-click to edit
- Checkbox to enable/disable engines on-the-fly

## Thematic search engines packages ready to install
- 12 Predefined packages for popular developer resources ([Search-Engines-Packages](https://github.com/jawehrung/Documentation_ContextualSearch/tree/master/Search-Engines-Packages))
  - General Search Engines
  - Q&A Forums
  - Code Repositories
  - Documentation Sites
  - Package Managers
  - Containers & Cloud
  - Code Examples
  - Learning Platforms
  - Developer Tools
  - Security Resources
  - API Directories
  - Design Resources
  
- One-click installation of multiple search engines
- Save time configuring your favorite search engines

<!-- Plugin description end -->

## 🚀 Quick Start

### Installation
1. Open **Settings/Preferences → Plugins**
2. Search for "ContextualSearch"
3. Click **Install** and restart IDE

### Configuration
1. Go to **Settings → Tools → ContextualSearch**
2. Click **+** to add a search engine
3. Enter:
   - **Name**: e.g., "Google"
   - **URL**: e.g., `https://www.google.com/search?q=%s`
4. Check **Enable** and click **OK**

### Usage
1. Select any text in editor, terminal, or console
2. Right-click → **Search with...**
3. Choose your search engine
4. Browser opens with search results

## 📋 Example Search Engines

| Name | URL Pattern |
|------|-------------|
| Google | `https://www.google.com/search?q=%s` |
| Stack Overflow | `https://stackoverflow.com/search?q=%s` |
| GitHub | `https://github.com/search?q=%s` |
| MDN Web Docs | `https://developer.mozilla.org/en-US/search?q=%s` |
| Maven Central | `https://search.maven.org/search?q=%s` |
| npm | `https://www.npmjs.com/search?q=%s` |
| PyPI | `https://pypi.org/search/?q=%s` |

## 🔧 Advanced Features

### Import/Export
Share your search engine configurations:
- Click **Import** to load engines from JSON
- Click **Export** to save your configuration
- Perfect for team standardization

### Multi-Context Support
Works seamlessly across:
- ✅ Code Editor
- ✅ Integrated Terminal
- ✅ Run/Debug Consoles
- ✅ Build Output Consoles

## 🤝 Contributing

Found a bug or have a feature request? Please open an issue on [GitHub](https://github.com/jawehrung/Documentation_ContextualSearch).

**Made with ❤️ for developers who value efficiency**
