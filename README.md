# QR-Menu

A fast, mobile-first digital menu for **A1 Bites** cafe. Customers scan a QR code at the table or counter and see the full menu with prices, plus one-tap buttons to call, message on WhatsApp, or get directions.

It is a **single `index.html` file** with no framework, no build step and no dependencies to install.

## Features

- Full menu with prices in ₹ (9 categories, 40 dishes)
- Sticky category tabs that highlight the section you are viewing
- Search box and a **Veg** filter
- Veg / non-veg markers on every dish
- **Call**, **WhatsApp** and **Directions** (Google Maps) buttons
- "Find us" section with phone numbers, location and optional address and hours
- Free-Campa offer banner
- Brand colours and logo matched to the cafe's printed menu and signboard
- Responsive layout, works on any phone size, safe-area aware (notches)
- Accessible: keyboard focus styles, labelled controls, respects reduced-motion
- Tiny (about 40 KB), loads quickly on mobile data

## Run it locally

**Option 1: just open it.** Double-click `index.html`. It works straight from the file.

**Option 2: VS Code Live Server** (auto-reload while editing)

1. Open the project folder in VS Code (**File > Open Folder**).
2. Install the **Live Server** extension.
3. Right-click `index.html` and choose **Open with Live Server**.

**Option 3: from the terminal** (also lets you test on your phone over Wi-Fi)

```bash
# Python
python -m http.server 5500

# or Node.js
npx serve
```

Then open `http://localhost:5500`.


| Field   | Meaning                                              |
| ------- | ---------------------------------------------------- |
| `n`     | Dish name                                            |
| `p`     | Price in rupees                                      |
| `veg`   | `true` for vegetarian (otherwise shown as non-veg)   |
| `note`  | Optional small description line                      |
| `badge` | Optional red tag next to the name                    |

### Colours

Colours are CSS variables at the top of the `<style>` block:

```css
--red: #EE1120;
--yellow: #F9C824;
--cream: #FAF3E9;
```

Change these and the whole page updates.

### Logo

The logo is embedded in the `<img id="logo">` tag as a small base64 image, and is also used as the browser tab and home-screen icon. To replace it, swap that `src` for your own image (a transparent PNG or SVG works best).

## Deploy

### GitHub Pages (free)

1. Push this repository to GitHub with `index.html` at the root.
2. Go to **Settings > Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then **Save**.
4. After a minute the site is live at `https://<your-username>.github.io/<repo-name>/`.

### Netlify Drop (free, no account setup needed to try)

Drag the project folder onto [app.netlify.com/drop](https://app.netlify.com/drop).

## Make the QR code

1. Deploy the site and copy its final URL.
2. Generate a QR code from that URL with any QR generator, and download it as SVG or a high-resolution PNG.
3. Print and test-scan it with a couple of different phones before mass printing.

Tip: use a custom domain if you can. A printed QR code breaks if the web address ever changes.

## Project structure

```
.
├── index.html   # the whole site (HTML, CSS, JS, logo)
└── README.md
```

## Notes

- Fonts (Baloo 2, Kaushan Script, DM Sans) load from Google Fonts. Offline, the page falls back to system fonts and still works.
- Prices were copied from the cafe's printed menu. Confirm any changes with the owner before publishing.
- The footer says "Please confirm taxes with the cafe". Edit it if prices are tax-inclusive.
