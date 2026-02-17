# Face Grid Generator (Auto-Crop & PDF Export)

A client-side web application that automatically detects faces in photos, crops them to a specific aspect ratio (27mm x 37mm), and arranges them into a 7x7 grid on an A4 PDF.

**Zero Maintenance • Zero Cost • Private (Client-Side Only)**

![Project Status](https://img.shields.io/badge/status-active-success)

## 🚀 Features

* **Automatic Face Detection:** Uses `face-api.js` to locate faces in uploaded photos.
* **Smart Cropping:** Automatically centers the face and crops to **27mm x 37mm**.
* **A4 Grid Layout:** Arranges **49 photos** (7 columns x 7 rows) per page with calculated margins.
* **PDF Export:** Generates a print-ready PDF using `jsPDF`.
* **Privacy First:** All processing happens in the browser. Photos are **never** uploaded to a server.

## 🛠️ Usage

### Option 1: Host Online (Recommended)
This is the easiest way to share the tool with others.

1.  Upload `index.html` to **GitHub Pages**, **Netlify**, or **Vercel**.
2.  Open the URL in any modern browser (Chrome, Edge, Safari).
3.  The app will automatically download the required AI models from a CDN the first time you visit.

### Option 2: Run Locally
**Note:** Due to browser security settings (CORS), you cannot simply double-click `index.html` to run it. You must use a local server.

**Using VS Code:**
1.  Install the **Live Server** extension.
2.  Right-click `index.html` and select **"Open with Live Server"**.

**Using Python:**
1.  Open your terminal/command prompt in the project folder.
2.  Run: `python -m http.server`
3.  Open `http://localhost:8000` in your browser.

## ⚙️ Configuration

You can customize the grid and cropping settings by editing the constants at the top of the `<script>` section in `index.html`:

```javascript
// Target dimensions for the cropped photo (in mm)
const TARGET_WIDTH_MM = 27;
const TARGET_HEIGHT_MM = 37;

// Adjusts the "zoom" level of the crop
// 1.8 = Close-up (Face only)
// 2.2 = Standard ID (Face + Neck)
// 2.5 = Wide (Face + Shoulders)
const ZOOM_FACTOR = 2.2; 

// Grid Layout
const COLS = 7;
const ROWS = 7;
```

## 📋 Requirements

To run this application, you need:

* **Modern Web Browser:**
    * Google Chrome (Recommended)
    * Microsoft Edge
    * Mozilla Firefox
    * Apple Safari
* **Internet Connection:**
    * Required for the initial load to fetch the AI models (`face-api.js` weights) from the CDN.
    * *Note: Once loaded, the app can technically run offline if your browser caches the resources.*
* **Hardware:**
    * A computer with at least 4GB of RAM is recommended for processing 40+ images smoothly.
    * No GPU is required (CPU is sufficient for this model).


## 🤝 Credits and Acknowledgements

This project uses the following open-source libraries:

* **[face-api.js](https://github.com/justadudewhohacks/face-api.js)** by Vincent Mühler
    * Used for face detection and landmark recognition in the browser.
    * License: MIT
* **[jsPDF](https://github.com/parallax/jsPDF)** by Parallax
    * Used for generating the PDF document client-side.
    * License: MIT


## 📄 License

MIT License

Copyright (c) 2024 Themis

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
