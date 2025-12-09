# Hamza Hotel Website - Deployment Guide

## Overview

This guide explains how to deploy the Hamza Hotel website with all assets properly configured.

---

## File Structure

Create the following folder structure:

```
hamza-hotel-website/
│
├── index.html              ← Rename hamza_hotel_website.html to this
│
└── assets/
    ├── founder-portrait.svg    ← From PNG_Icon.svg
    ├── text-logo.svg           ← From Frame_1.svg  
    ├── full-logo.svg           ← From PNG_Icon_Logo.svg (optional)
    ├── favicon.svg             ← From PNG_Icon.svg (copy)
    ├── mutton-biryani.jpg      ← Food photo (you provide)
    ├── beja-fry.jpg            ← Food photo (you provide)
    └── chicken-kebab.jpg       ← Food photo (you provide)
```

---

## Image Specifications

### 1. FOUNDER PORTRAIT (Icon)

| Property | Value |
|----------|-------|
| **Source File** | `PNG_Icon.svg` or `PNG_Icon.jpg` |
| **Rename To** | `founder-portrait.svg` |
| **Aspect Ratio** | **1:1.28** (Width:Height) |
| **Display Sizes** | |
| Desktop | 280px × 358px |
| Tablet | 220px × 282px |
| Mobile | 150px × 192px |
| **Location in Code** | Hero section, Legacy section |

**How to calculate dimensions:**
- Width × 1.28 = Height
- Example: 280 × 1.28 = 358.4 ≈ 358px

---

### 2. TEXT LOGO (Hamza Hotel text with flourishes)

| Property | Value |
|----------|-------|
| **Source File** | `Frame_1.svg` or `Text_Logo.jpg` |
| **Rename To** | `text-logo.svg` |
| **Aspect Ratio** | **1.26:1** (Width:Height) |
| **Display Sizes** | |
| Desktop | 400px × 317px |
| Tablet | 320px × 254px |
| Mobile | 240px × 190px |
| **Location in Code** | Hero section (beside portrait) |

**How to calculate dimensions:**
- Width ÷ 1.26 = Height
- Example: 400 ÷ 1.26 = 317.46 ≈ 317px

---

### 3. FULL LOGO (Icon + Text Combined)

| Property | Value |
|----------|-------|
| **Source File** | `PNG_Icon_Logo.svg` or `PNG_Icon_Logo.jpg` |
| **Rename To** | `full-logo.svg` |
| **Aspect Ratio** | **1.87:1** (Width:Height) |
| **Display Sizes** | |
| Desktop | 600px × 321px |
| Tablet | 500px × 267px |
| Mobile | 350px × 187px |
| **Location in Code** | Hero section (alternative layout) |

**How to calculate dimensions:**
- Width ÷ 1.87 = Height
- Example: 600 ÷ 1.87 = 320.86 ≈ 321px

---

### 4. FOOD IMAGES

| Property | Value |
|----------|-------|
| **Format** | JPG (optimized for web) |
| **Dimensions** | **400px × 400px** (1:1 square) |
| **File Size** | Under 100KB each |
| **Style** | Well-lit, appetizing, professional |

**Required Images:**

| Filename | Dish |
|----------|------|
| `mutton-biryani.jpg` | Mutton Biryani |
| `beja-fry.jpg` | Beja Fry |
| `chicken-kebab.jpg` | Chicken Kebab |

**Tips for food photography:**
- Natural lighting preferred
- Clean background (white/neutral)
- Show steam if possible (freshness)
- Can apply slight sepia filter to match brand

---

### 5. FAVICON

| Property | Value |
|----------|-------|
| **Source** | Copy from `PNG_Icon.svg` |
| **Rename To** | `favicon.svg` |
| **Size** | Any (SVG is scalable) |
| **Alternative** | Create 32×32px PNG version |

---

## Step-by-Step Deployment

### Step 1: Prepare Your Files

1. Download `hamza_hotel_website.html` from outputs
2. Rename it to `index.html`
3. Create `assets` folder in same directory

### Step 2: Rename and Copy Images

| Your File | Rename To | Place In |
|-----------|-----------|----------|
| `PNG_Icon.svg` | `founder-portrait.svg` | `assets/` |
| `Frame_1.svg` | `text-logo.svg` | `assets/` |
| `PNG_Icon_Logo.svg` | `full-logo.svg` | `assets/` |
| `PNG_Icon.svg` | `favicon.svg` | `assets/` |

### Step 3: Add Food Images

Place your food photos in `assets/` folder with exact names:
- `mutton-biryani.jpg`
- `beja-fry.jpg`
- `chicken-kebab.jpg`

### Step 4: Test Locally

1. Open `index.html` in a web browser
2. Check all images load correctly
3. Test on mobile (use browser dev tools)
4. Click all WhatsApp buttons to verify links

### Step 5: Deploy

**Option A: Simple Static Hosting**
- Upload entire `hamza-hotel-website` folder to:
  - Netlify (free)
  - Vercel (free)
  - GitHub Pages (free)

**Option B: Traditional Hosting**
- Upload via FTP to your web hosting
- Set `index.html` as default page

---

## Code Customization Reference

### To Change WhatsApp Number

Find and replace all instances of:
```
918008004202
```

With your preferred number (without + symbol).

---

### To Use Full Logo Instead of Split Layout

In the HTML, find this section in the Hero:

```html
<!-- OPTION 1: Separate Icon + Text Logo (Recommended for large screens) -->
<div class="hero__logo-container">
    ...
</div>
```

Comment it out and uncomment OPTION 2 below it:

```html
<!-- OPTION 2: Full Combined Logo (Alternative - uncomment to use) -->
<div class="hero__full-logo">
    <img src="assets/full-logo.svg" ...>
</div>
```

---

### To Change Operating Hours

Find this in the Visit section:

```html
<div class="visit__info-value">
    Open Daily<br>
    7:00 AM – 5:00 AM<br>
```

Edit the times as needed.

---

### To Update Google Maps

Find the iframe in Visit section and replace the `src` URL with your actual Google Maps embed code:

1. Go to Google Maps
2. Search "Hamza Hotel Shivajinagar"
3. Click Share → Embed a map
4. Copy the iframe src URL
5. Replace in code

---

## Brand Colors (CSS Variables)

These are defined at the top of the CSS and match your brand:

```css
--color-black-pure: #010101;
--color-black-deep: #131313;    /* Primary text */
--color-black-text: #1D1E1E;
--color-gray-dark: #333333;     /* Body text */
--color-gray-medium: #676767;   /* Secondary text */
--color-gray-light: #919191;
--color-gray-border: #D1D1D1;   /* Borders */
--color-gray-subtle: #E5E5E5;
--color-white-off: #FAFAFA;     /* Primary background */
--color-cream: #F5F2ED;         /* Alternate background */
```

---

## Typography

The website uses:
- **Primary**: Times New Roman (matches brand)
- **Fallback**: Playfair Display (Google Font)
- **System Fallback**: Georgia, serif

This matches your brand guidelines exactly.

---

## Responsive Breakpoints

| Device | Width | Layout Changes |
|--------|-------|----------------|
| Desktop | > 1024px | Full layout, side-by-side elements |
| Tablet | 768-1024px | Stacked logo, 2-column menu |
| Mobile | < 768px | Single column, hamburger menu |

---

## Checklist Before Going Live

- [ ] All images renamed and in `assets/` folder
- [ ] Food images are 400×400px JPG format
- [ ] WhatsApp number is correct
- [ ] Google Maps shows correct location
- [ ] Operating hours are accurate
- [ ] Tested on mobile device
- [ ] All buttons/links work
- [ ] Page loads quickly (< 3 seconds)

---

## File Size Optimization

For best performance:

| File Type | Target Size |
|-----------|-------------|
| SVG logos | Under 50KB each |
| Food JPGs | Under 100KB each |
| Total page | Under 500KB |

Use [TinyPNG](https://tinypng.com) or [Squoosh](https://squoosh.app) to compress images.

---

## Support

If you need to make changes:
1. Edit the HTML file directly
2. CSS is embedded in the `<style>` tag
3. JavaScript is at the bottom of the file

All code is well-commented for easy modification.
