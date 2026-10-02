# 🎬 Psygn0sis Color-Changing Jellyfin Theme

The theme combines custom CSS with a dynamic JavaScript ribbon that automatically extracts color from each item's poster and applies it to the ribbon.

A custom **desktop-focused Jellyfin theme** designed to give the detail page a cleaner, darker, more cinematic look while keeping the familiar Jellyfin interface.

![Dynamic Color Ribbon](https://github.com/psygn0s/jellyfin-themes/blob/main/jellyfin-colorchange/Screenshots/1.png)

![Psygn0sis Jellyfin Theme](https://github.com/psygn0s/jellyfin-themes/blob/main/jellyfin-colorchange/Screenshots/4.png)

![Psygn0sis Jellyfin Theme](https://github.com/psygn0s/jellyfin-themes/blob/main/jellyfin-colorchange/Screenshots/3.png)

![Dynamic Color Ribbon](https://github.com/psygn0s/jellyfin-themes/blob/main/jellyfin-colorchange/Screenshots/1.png)

![Dynamic Color Ribbon](https://github.com/psygn0s/jellyfin-themes/blob/main/jellyfin-colorchange/Screenshots/5.png)


---

# ✨ Features

## 🎨 Dynamic Color Ribbon

## 🌄 Cinematic Backdrop

## 🌑 Scrolling Dark Gradient

## 🖼️ Custom Detail Logo

## 🎞️ Card Hover Effects

## 📋 Custom Metadata Layout

## 🧹 Cleaner Detail Page

## 👥 Improved Cast & Crew

---

# 🚀 Installation

# 🔌 Step 1 — Install JavaScript Injector Plugin.

In Jellyfin, open:

**Dashboard → Plugins → Catalog**

Click the **⚙️ Repository** button.

Select **Add Repository**.

Name: `JavaScript Injector`

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

# 🧩 Step 2 — Install theme.

🎨 Install the Dynamic Ribbon JavaScript

After restarting Jellyfin, open:

**Dashboard → Plugins → JS Injector**

Click:

**Add Script**

Give the script a name such as:

`Psygn0sis Theme`

Paste the following into the field.

```Javascript
const script = document.createElement('script');
script.src = 'https://cdn.jsdelivr.net/gh/psygn0s/jellyfin-themes@latest/jellyfin-colorchange/Get-color.js';
script.async = true;
document.head.appendChild(script);
```
Make sure the script is **Enabled**.

Click **Save**.

---

# 🎨 Step 3 — Install the CSS Theme

Copy this into Jellyfin → Dashboard → Branding → Custom CSS:
```Javascript
@import url("https://cdn.jsdelivr.net/gh/psygn0s/jellyfin-themes@latest/jellyfin-colorchange/color-change.css");
```

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

The theme relies on Jellyfin's existing DOM structure and CSS classes. Major Jellyfin frontend updates may therefore require changes to the CSS selectors.

> ⚠️ **Note:** Custom CSS and JavaScript are generally version-dependent. If Jellyfin changes its frontend structure, some features may need to be updated.

---

# ⭐ Credits

Created for the Jellyfin community by **Psygn0sis**.

Built using:

* [Jellyfin](https://jellyfin.org/)
* [Jellyfin JavaScript Injector](https://github.com/n00bcodr/Jellyfin-JavaScript-Injector)

---

