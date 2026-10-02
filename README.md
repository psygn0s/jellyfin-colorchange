# 🎬 Psygn0sis Color-Changing Jellyfin Theme

A custom **desktop-focused Jellyfin theme** designed to give the detail page a cleaner, darker, more cinematic look while keeping the familiar Jellyfin interface.

![Psygn0sis Jellyfin Theme](screenshots/main-detail-page.png)

The theme combines custom CSS with a dynamic JavaScript ribbon that automatically extracts color from each item's poster.

---

# ✨ Features

## 🎨 Dynamic Color Ribbon

The detail-page ribbon automatically picks up a color from the item's primary poster.

![Dynamic Color Ribbon](screenshots/dynamic-ribbon.png)

The JavaScript:

* Detects the current Jellyfin item
* Retrieves the primary poster
* Samples the image
* Calculates a usable average color
* Caches colors per item
* Detects navigation between items
* Applies the color automatically

---

## 🌄 Cinematic Backdrop

The backdrop remains fixed while the page content scrolls naturally over it.

![Cinematic Backdrop](screenshots/cinematic-backdrop.png)

This keeps the artwork visible while preventing the background from moving awkwardly with the detail-page content.

---

## 🌑 Scrolling Dark Gradient

A gradual dark gradient is applied toward the lower portion of the page.

![Scrolling Dark Gradient](screenshots/dark-gradient.png)

This improves readability around the metadata and controls while keeping the upper portion of the artwork visible.

---

## 🖼️ Custom Detail Logo

The Jellyfin detail-page logo is repositioned and scaled for a cleaner desktop presentation.

![Custom Detail Logo](screenshots/detail-logo.png)

---

## 🎞️ Card Hover Effects

Cards smoothly enlarge when hovered, giving the browsing interface a more interactive feel.

![Card Hover Effect](screenshots/card-hover.png)

---

## 📋 Custom Metadata Layout

The detail page is reorganized to prioritize the information that matters most.

![Custom Metadata Layout](screenshots/metadata-layout.png)

The layout prioritizes:

* Tagline
* Birth/death information
* Overview
* Item details
* Tags
* Cast & crew

---

## 🧹 Cleaner Detail Page

Unnecessary sections are removed from the customized layout:

* Genres
* Track selections
* External links

The result is a cleaner detail page with less visual clutter.

---

## 👥 Improved Cast & Crew

Additional spacing is added around cast and crew sections to give the lower portion of the detail page more breathing room.

![Cast & Crew](screenshots/cast-crew.png)

---

# 📸 Screenshots

Here are some examples of the theme in action.

## 🎬 Movie Detail Page

![Movie Detail Page](screenshots/movie-detail.png)

## 📺 TV Show Detail Page

![TV Show Detail Page](screenshots/tv-show-detail.png)

## 🎨 Poster-Based Ribbon

![Poster-Based Ribbon](screenshots/dynamic-ribbon.png)

## 🌑 Cinematic Backdrop

![Cinematic Backdrop](screenshots/cinematic-backdrop.png)

---

# 🚀 Installation

This theme uses **two components**:

| File                     | Purpose                     |
| ------------------------ | --------------------------- |
| `color-change-theme.css` | Main Jellyfin theme         |
| `Get-color.js`           | Dynamic poster-color ribbon |

The JavaScript is installed through the **Jellyfin JavaScript Injector** plugin.

---

# 🔌 Step 1 — Install JavaScript Injector

In Jellyfin, open:

**Dashboard → Plugins → Catalog**

Click the **⚙️ Repository** button.

Select **Add Repository**.

Enter:

**Name**

`JavaScript Injector`

### Jellyfin 10.11

```text
https://raw.githubusercontent.com/n00bcodr/jellyfin-plugins/main/10.11/manifest.json
```

### Jellyfin 12+

```text
https://raw.githubusercontent.com/n00bcodr/jellyfin-plugins/main/12/manifest.json
```

Click **Save**.

Return to the Plugin Catalog and search for:

**JavaScript Injector**

Click **Install** and restart Jellyfin when prompted.

For more information, visit the official **[Jellyfin JavaScript Injector GitHub repository](https://github.com/n00bcodr/Jellyfin-JavaScript-Injector)**.

---

# 🧩 Step 2 — Install `Get-color.js`

After restarting Jellyfin, open:

**Dashboard → Plugins → JS Injector**

Click:

**Add Script**

Give the script a name such as:

`Psygn0sis Dynamic Ribbon Color`

Open **`Get-color.js`** from this project and copy the entire contents into the JavaScript Injector editor.

Make sure the script is **Enabled**.

Click **Save**.

---

# 🎨 Step 3 — Install the CSS Theme

Open:

**Dashboard → General → Custom CSS**

Copy the contents of:

**`color-change-theme.css`**

Paste it into Jellyfin's **Custom CSS** field.

Click **Save**.

---

# 🔄 Step 4 — Refresh Jellyfin

Perform a hard refresh after installing the CSS and JavaScript.

### Windows / Linux

`Ctrl + F5`

### macOS

`Cmd + Shift + R`

The theme should now be active.

---

# 🛠️ Customization

## 🌑 Backdrop Darkness

The scrolling gradient can be adjusted in `color-change-theme.css`:

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

## 🎞️ Card Hover Size

The card hover effect is controlled by:

```css
transform: scale(1.1);
```

For a more subtle effect:

```css
transform: scale(1.05);
```

---

## 🎨 Ribbon Opacity

The ribbon opacity is controlled inside `Get-color.js`.

Current setting:

```javascript
opacity: 0.8;
```

For a completely solid ribbon:

```javascript
opacity: 1;
```

For a more transparent ribbon:

```javascript
opacity: 0.6;
```

---

# 📁 Project Structure

```text
/
├── color-change-theme.css
├── Get-color.js
├── README.md
└── screenshots/
    ├── main-detail-page.png
    ├── movie-detail.png
    ├── tv-show-detail.png
    ├── dynamic-ribbon.png
    ├── cinematic-backdrop.png
    ├── dark-gradient.png
    ├── detail-logo.png
    ├── card-hover.png
    ├── metadata-layout.png
    └── cast-crew.png
```

---

# 🖥️ Compatibility

Designed primarily for:

* 🖥️ Jellyfin Desktop Web
* 🎬 Jellyfin Detail Pages
* 🌐 Modern Chromium-based browsers
* 🦊 Firefox
* 🔌 Jellyfin JavaScript Injector

The theme relies on Jellyfin's existing DOM structure and CSS classes. Major Jellyfin frontend updates may therefore require changes to the CSS selectors.

> ⚠️ **Note:** Custom CSS and JavaScript are generally version-dependent. If Jellyfin changes its frontend structure, some features may need to be updated.

---

# 🔗 Useful Links

* 🎬 **[Jellyfin](https://jellyfin.org/)**
* 💻 **[Jellyfin GitHub](https://github.com/jellyfin/jellyfin)**
* 🔌 **[Jellyfin JavaScript Injector](https://github.com/n00bcodr/Jellyfin-JavaScript-Injector)**

---

# ⭐ Credits

Created for the Jellyfin community by **Psygn0sis**.

Built using:

* [Jellyfin](https://jellyfin.org/)
* [Jellyfin JavaScript Injector](https://github.com/n00bcodr/Jellyfin-JavaScript-Injector)

---

## 🎬 Make Jellyfin Yours

**Customize it. Tune it. Make every title feel like its own screen.**
