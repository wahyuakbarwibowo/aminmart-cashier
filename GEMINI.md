# Project Overview

Aminmart Cashier is a modern, responsive web landing page for a smart cashier mobile application, tailored for retail businesses and digital sales management in Indonesia. The site is built with HTML5, Tailwind CSS, and standard JavaScript.

# Key Pages & Functionality

- **Home (`index.html`)**: Main landing page with hero section, features, and download call-to-action.
- **Support (`contact.html`)**: Contact details and support form.
- **Install Guide (`install.html`)**: Step-by-step instructions for APK installation.
- **Account Policy (`delete-account.html`)**: Data deletion policy for compliance.
- **Statistics (`stats.html`, `stats.json`)**: Basic client-side usage tracking.

# Social Sharing Metadata (SEO & WhatsApp)

To ensure the website appears correctly when shared on platforms like WhatsApp, Telegram, or Facebook (Open Graph), add the following `<meta>` tags inside the `<head>` section of `index.html` (and other pages if necessary):

```html
<!-- Open Graph Metadata for Social Sharing -->
<meta property="og:title" content="Aminmart Cashier - Solusi Kasir Pintar" />
<meta property="og:description" content="Aplikasi kasir serbaguna untuk pencatatan transaksi toko retail dan manajemen penjualan produk digital secara mandiri." />
<meta property="og:image" content="https://your-domain.com/cashier-icon.png" />
<meta property="og:url" content="https://your-domain.com/index.html" />
<meta property="og:type" content="website" />

<!-- Twitter Card Metadata -->
<meta name="twitter:card" content="summary_large_image" />
<meta name="twitter:title" content="Aminmart Cashier - Solusi Kasir Pintar" />
<meta name="twitter:description" content="Aplikasi kasir serbaguna untuk pencatatan transaksi toko retail dan manajemen penjualan produk digital secara mandiri." />
<meta name="twitter:image" content="https://your-domain.com/cashier-icon.png" />
```

*Note: Replace `https://your-domain.com` with your actual hosted domain or URL.*

# Development Conventions

- **Styling**: Tailwind CSS is used via CDN. Custom styles (like glassmorphism) are defined in the `<style>` block.
- **Configuration**: `config.js` is used for global components like the Navbar.
- **Hosting**: Designed as a static site suitable for deployment on GitHub Pages or any standard web server.

# How to Run

1. Open `index.html` in a local web browser.
2. Ensure you have internet access to load Tailwind CSS and Google Fonts.
