# DeepSeek Translator for Obsidian

Translate selected English text to Chinese inside Obsidian using the DeepSeek API. Results are written directly back into your note.

---

## Features

- Translates selected text, or the entire note if nothing is selected
- Three output modes: replace selection / append below / create new note
- Trigger via Command Palette (`Ctrl+P`) or editor right-click menu
- Built-in SEO-focused translation prompt, preserves Markdown formatting
- Loading indicator while translating, clear error messages on failure

---

## Installation

### Option 1: Direct install (recommended)

1. Download `main.js` and `manifest.json`
2. Create a folder in your Obsidian vault:
   ```
   <your-vault>/.obsidian/plugins/obsidian-deepseek-translator/
   ```
3. Place both files into that folder
4. Open Obsidian → **Settings** → **Community plugins**
5. Disable Safe Mode → Refresh → Enable **DeepSeek Translator**

### Option 2: Build from source (developers)

```bash
git clone <repo-url>
cd ObsidianSEOplugin
npm install
npm run build
```

Then install `main.js` and `manifest.json` using Option 1.

---

## Usage

**Command Palette:**
1. Select some English text (or select nothing to translate the whole note)
2. Press `Ctrl+P` to open the Command Palette
3. Search for and run **Translate to Chinese**

**Right-click menu:**
1. Select some English text
2. Right-click → **Translate to Chinese**

---

## Settings

Open Obsidian → **Settings** → **DeepSeek Translator**

| Setting | Description |
|---------|-------------|
| **DeepSeek API Key** | Your API key, starting with `sk-...` |
| **Output Mode** | Replace selection / Append below / New note |
| **System Prompt** | Instructions sent to the AI. Pre-filled with an SEO translation template — fully customizable |
| **Temperature** | Output randomness (0–1). Default 0.3 is recommended for translation |

---

## Getting a DeepSeek API Key

1. Go to [platform.deepseek.com](https://platform.deepseek.com)
2. Sign up or log in
3. Navigate to **API Keys** → **Create API Key**
4. Copy the key (starts with `sk-...`) and paste it into the plugin settings

> **Keep your API key private.** It is tied to your account and has associated costs.

---

## Error Reference

| Error | Cause | Fix |
|-------|-------|-----|
| API Key invalid | Key is wrong or expired | Check the API Key in settings |
| Insufficient balance | DeepSeek account has no credits | Top up at platform.deepseek.com |
| Too many requests | Rate limit hit | Wait a moment and try again |
| Network timeout | Connection issue | Check your internet and retry |
