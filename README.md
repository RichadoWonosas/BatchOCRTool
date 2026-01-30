# Batch Template OCR Tool

**Version**: v2.6

**Core Engine**: Tesseract.js v5

This is a browser-based, pure frontend batch OCR tool. It allows users to define "Recognition Templates" (by selecting specific areas on an image) and then automatically batch process a large number of structurally identical images (such as invoices, forms, ID cards), extracting text from the specified areas into a CSV table.

## ✨ Core Features

* **🛡️ Privacy & Security**: Based on `Tesseract.js`, all recognition processes run entirely in your **local browser**. Images are **never uploaded** to any server.

* **📂 Smart File Management**:

  * Supports **drag-and-drop** for folders or multiple files.

  * Automatically **groups** images based on resolution (e.g., `1920x1080`, `800x600`), solving issues with inconsistent image dimensions from different sources.

* **🎨 Interactive Template Design**:

  * Freely draw recognition areas on the Canvas.

  * Supports **dragging to move** recognition boxes.

  * Supports **resizing** (all boxes come with resize handles).

  * Supports mouse wheel zoom for the canvas and fullscreen editing mode.

* **⚙️ Powerful Configuration Management**:

  * Supports **Import/Export Configuration (JSON)**: Draw your template once, save it, and reuse it later or share it with colleagues.

  * **Field Reordering**: Freely adjust the order of fields, determining the column order in the exported CSV.

* **📊 Batch Processing & Export**:

  * Supports multi-language recognition (English, Chinese, Japanese, etc.).

  * Real-time progress bar display.

  * One-click export to **CSV** file (compatible with Excel).

## 🚀 Quick Start

### 1. How to Run

This tool is a single-file HTML application.

* **Recommended**: Run using the "Live Server" extension in VS Code.

* **Direct Open**: Double-click the `.html` file to open it in Chrome or Edge browser (internet connection required to load the Tesseract core library).

### 2. Workflow

#### Step 1: Import Images

* Drag a **folder** containing images directly into the gray area.

* Or click the "Select Folder" / "Select Files" buttons.

* *Tip: The tool will automatically analyze image dimensions and group them.*

#### Step 2: Define Fields

* Enter the field name in the input box (e.g., `InvoiceCode`, `Date`, `Amount`) and press **Enter** to add.

* In the list below, use the `↑` `↓` buttons to adjust the field order (this affects the CSV column order).

* *Advanced: If you have a previously saved `.json` configuration file, click "Import Config" to skip this step and Step 3.*

#### Step 3: Set Recognition Areas (Draw Boxes)

1. Select a resolution group from the "Current Size Group" dropdown menu.

2. Click the field you want to draw in the left list (e.g., `InvoiceCode`).

3. Hold the left mouse button on the image to **draw a box**.

4. **Adjustments**:

   * **Move**: Click and drag the field name label at the top of the box.

   * **Resize**: Drag the small white square handle at the bottom right of the box.

5. *Note: If your images have multiple different resolutions, remember to switch "Size Groups" and draw boxes for each resolution respectively.*

#### Step 4: Batch Recognition

1. Select the recognition language (default is English; switch to `Chinese Simplified` for Chinese characters).

2. Click **"🚀 Start Batch Recognition"**.

3. Wait for the progress bar to complete, then click **"💾 Download CSV"** to save the results.

## ⚠️ FAQ & Notes

1. **Why is the recognition accuracy low?**

   * Tesseract.js is a lightweight engine; it has limited effectiveness on **handwritten text** or images with **complex backgrounds**.

   * It is recommended to ensure the recognition area contains only text, avoiding excess borders or noise.

   * Ensure the correct language package is selected (e.g., if the image contains Chinese, you must select `Chinese`).

2. **Mobile Compatibility?**

   * The current version is optimized for **Desktop (PC/Mac)** (mouse operations). Drawing boxes is not supported on mobile devices.

3. **Where did my data go?**

   * All data is processed in your browser's memory. Data will be lost if you refresh the page. Please ensure you download the CSV or export the configuration in time.

## 📜 License

This project is open source and based on the MIT License. It uses the [Tesseract.js](https://github.com/naptha/tesseract.js) library.
