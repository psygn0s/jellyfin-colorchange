


# 🎬 Psygn0sis Color-Changing Jellyfin Theme.

A custom **desktop-focused Jellyfin CSS theme** designed to give the Jellyfin detail page a cleaner, more cinematic appearance while keeping the interface familiar and functional.

It adds a **fixed cinematic backdrop, scrolling dark gradient, poster-based color ribbon, enlarged metadata, custom section ordering, card hover effects, and improved cast & crew spacing.**

---

## ✨ Features

🎨 **Dynamic Color Ribbon**
Automatically matches the detail-page ribbon to the item's poster using the companion JavaScript userscript.

🌄 **Cinematic Backdrop**
Keeps the backdrop fixed while the page content scrolls naturally over it.

🌑 **Scrolling Dark Gradient**
Gradually darkens the lower portion of the detail page for improved readability while preserving the artwork near the top.

🖼️ **Custom Detail Logo**
Repositions and scales Jellyfin's detail-page logo for a cleaner desktop layout.

🎞️ **Card Hover Effects**
Cards smoothly enlarge when hovered for a more interactive browsing experience.

📋 **Custom Metadata Layout**
Reorganizes detail-page information to prioritize:

* Tagline
* Birth/death information
* Overview
* Item details
* Tags
* Cast & crew

🧹 **Cleaner Detail Page**
Removes unnecessary sections such as:

* Genres
* Track selections
* External links

while preserving the rest of the Jellyfin interface.

👥 **Improved Cast & Crew Spacing**
Adds additional breathing room around cast and crew sections.

The project also includes a companion JavaScript userscript that extracts a color from the item's primary poster and applies it to the Jellyfin detail ribbon.

The script:

* Detects the current Jellyfin item
* Retrieves the primary poster
* Samples the image
* Calculates an average usable color
* Caches colors per item
* Automatically detects navigation between items
* Applies the color to the detail ribbon

---

## 🖥️ Designed For

This CSS is primarily designed for the **Jellyfin desktop web interface**.

It uses Jellyfin's existing DOM structure and CSS classes, so appearance may change if Jellyfin significantly changes its frontend.

> ⚠️ **Note:** Custom CSS is generally version-dependent. If Jellyfin updates its UI, some selectors may need to be adjusted.

---

# 🚀 Installation

# 🎨 Install Dynamic Ribbon Color Java Script.

### 🔗 Companion Script

**`Get-color.js`**

I🔌 Install Jellyfin JavaScript Injector
Step 1 — Open the Plugin Catalog

In Jellyfin, go to:

Dashboard → Plugins → Catalog

Click the ⚙️ repository settings button.

Step 2 — Add the JavaScript Injector Repository

Click ➕ Add Repository.

Give it a name such as:

JavaScript Injector

Then add the repository URL appropriate for your Jellyfin version.

Jellyfin 10.11
https://raw.githubusercontent.com/n00bcodr/jellyfin-plugins/main/10.11/manifest.json
Jellyfin 12
https://raw.githubusercontent.com/n00bcodr/jellyfin-plugins/main/12/manifest.json

Click Save.

Step 3 — Install the Plugin

Return to the Catalog.

Search for:

JavaScript Injector

Click Install.

Restart Jellyfin after installation.

You should now see a new "js injector" under "Plugins" in the left side.
Click "Add Script" and paste the contents of "Get-color.js.
Click "Save".
---

### 🔗 Install custom CSS.

## 1. Open Jellyfin

Open your Jellyfin server in a web browser.

Go to:

**Dashboard → General → Custom CSS**

Depending on your Jellyfin version, the location of the Custom CSS field may vary.

---

## 2. Copy the CSS

Copy the contents of the project's CSS file:

**`color-change-theme.css`**

Paste it into Jellyfin's **Custom CSS** field.

Save your changes.

---

## 3. Refresh Jellyfin

After saving:

**Linux / Windows**

`Ctrl + F5`

**macOS**

`Cmd + Shift + R`

A hard refresh ensures that the new CSS is loaded instead of an older cached version.

---

# 🛠️ Customization

Most visual adjustments can be made directly in the CSS.

### Backdrop Darkness

The gradient can be adjusted here:

```css
background: linear-gradient(
  to bottom,
  rgba(0, 0, 0, 0) 0%,
  rgba(23, 23, 23, 0.15) 15vh,
  rgba(23, 23, 23, 0.35) 30vh,
  rgba(23, 23, 23, 0.65) 45vh,
  rgba(23, 23, 23, 0.90) 55vh,
  #171717 99vh,
  #171717 100%
);
```

Increase the alpha values to make the gradient darker.

---

### Card Hover Size

The hover scale is controlled here:

```css
transform: scale(1.1);
```

For example:

```css
transform: scale(1.05);
```

creates a more subtle effect.

---

### Ribbon Opacity

The companion JavaScript currently uses:

```javascript
opacity: 0.8;
```

Change this value to adjust the ribbon transparency.

For example:

```javascript
opacity: 1;
```

creates a fully opaque ribbon.

---

# 📁 Project Structure

```text
/
├── custom.css
├── ribbon-color.js
└── README.md
```

---

# 🧩 Compatibility

Built for:

* 🖥️ Jellyfin Desktop Web
* 🎬 Jellyfin Detail Pages
* 🌐 Modern Chromium-based browsers
* 🦊 Firefox
* 🧩 Userscript managers

Because Jellyfin's frontend can change between releases, compatibility may vary between Jellyfin versions.

For Jellyfin documentation and current project information, visit the official [Jellyfin website](https://jellyfin.org/) and [Jellyfin GitHub](https://github.com/jellyfin/jellyfin).

---

# 💡 Recommended Setup

For the full experience, use both components:

| Component         | Purpose                                      |
| ----------------- | -------------------------------------------- |
| `custom.css`      | Layout, backdrop, gradient, cards & metadata |
| `ribbon-color.js` | Dynamic poster-based ribbon color            |

Together they create a more **cinematic, personalized Jellyfin detail page** without replacing the Jellyfin interface.

---

# ⭐ Credits

Built for the Jellyfin community.

Powered by:

* [Jellyfin](https://jellyfin.org/)
* [Jellyfin GitHub](https://github.com/jellyfin/jellyfin)

---

## 🎬 Make Jellyfin Yours

**Customize it. Tune it. Make every title feel like its own screen.**
