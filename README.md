---
title: Bulk PDF Link & Image Replacer
emoji: 📎
colorFrom: blue
colorTo: purple
sdk: gradio
sdk_version: 3.50.2
app_file: app.py
pinned: false
---

**# 📎 Bulk PDF Link & Image Replacer**

A simple and practical web-based tool for processing multiple PDF files at once.

**\*\*Bulk PDF Link & Image Replacer\*\*** helps you replace PDF hyperlinks and first-page images in bulk without manually opening and editing every PDF one by one.

You can upload multiple PDF files directly, or provide a \`.txt\` file containing PDF URLs. The application downloads the PDFs, applies the selected replacements, optionally compresses the output files, and finally provides all processed PDFs together in a ZIP file.

The original PDF files are never modified.

**---**

**## ✨ Why This Project?**

Working with a large number of PDF files can become repetitive when the same link or image needs to be changed in every document.

For example, imagine having 50 or 100 PDFs where:

\- The same old website link needs to be replaced

\- The first-page image needs to be updated

\- A clickable link needs to be added to the first page

\- PDFs need to be compressed

\- Output files need consistent names

Doing this manually takes a lot of time.

This project was created to make that process much faster.

Instead of editing every PDF separately, you can provide all your PDFs, select the required options, click **\*\*START BULK REPLACEMENT\*\***, and let the application process everything automatically.

**---**

**## 🚀 Features**

**### 📄 1. Bulk PDF Upload**

Upload multiple PDF files at the same time.

The application processes the PDFs one by one and shows the progress in the interface.

**---**

**### 🔗 2. Replace PDF Hyperlinks**

Enter a new URL and replace existing PDF hyperlinks.

You can choose:

\- Replace PDF hyperlinks

\- Replace all existing links

\- Add a clickable link over the entire first page

The whole-page link option works in addition to existing links.

**---**

**### 🖼️ 3. Replace First-Page Image**

Upload a replacement image and use it to replace an image on the first page of each PDF.

Supported image formats:

\- PNG

\- JPG

\- JPEG

\- WEBP

If multiple images are present on the first page, you can choose:

\- **\*\*Largest image\*\***

\- **\*\*First image\*\***

**---**

**### 🧩 4. Handle PDFs Without a First-Page Image**

If a PDF doesn't contain an image on its first page, the application can insert the uploaded replacement image.

You can choose to insert the image covering the whole first page.

**---**

**### 📐 5. Preserve Image Aspect Ratio**

The application can preserve the original aspect ratio of the replacement image.

This helps prevent unnecessary stretching or distortion.

**---**

**### 🗜️ 6. PDF Compression**

The application includes an optional PDF compression feature.

You can specify a target size range:

\`\`\`text

Min size (KB)

Max size (KB)

\`\`\`

The default target range is:

\`\`\`text

200 KB - 400 KB

\`\`\`

The application first performs lossless PDF optimization.

If the PDF is still larger than the maximum target size, embedded images are progressively recompressed at lower JPEG quality levels.

If a PDF is already smaller than the minimum size, it is not artificially inflated.

**---**

**### 📝 7. Process PDFs From URLs**

You don't always need to download PDFs manually.

The application also supports a \`.txt\` file containing PDF URLs.

Example:

\`\`\`text

https\://example.com/document1.pdf

https\://example.com/document2.pdf

https\://example.com/document3.pdf

\`\`\`

One URL should be placed on each line.

Empty lines are ignored.

Lines beginning with \`#\` are treated as comments.

**---**

**### 🔄 8. Mixed Processing**

You can provide:

\- Directly uploaded PDF files

\- A \`.txt\` file containing PDF URLs

Both sources can be processed in the same batch.

**---**

**### 📁 9. Keep Original Filenames**

You can choose to keep the original PDF filenames.

For example:

\`\`\`text

invoice.pdf

report.pdf

document.pdf

\`\`\`

will remain the same in the output when the option is enabled.

**---**

**### ✏️ 10. Custom Output Filename**

You can provide your own output filename.

For a single PDF:

\`\`\`text

my-report.pdf

\`\`\`

For multiple PDFs:

\`\`\`text

my-report_1.pdf

my-report_2.pdf

my-report_3.pdf

\`\`\`

**---**

**### 📦 11. ZIP Output**

After processing is complete, the application creates a ZIP file containing the generated PDFs and the processing log.

Default ZIP filename:

\`\`\`text

bulk_pdf_replacer_output.zip

\`\`\`

You can also provide your own ZIP filename.

**---**

**### 📊 12. Live Processing Log**

The interface displays processing information while the PDFs are being handled.

Each file can report:

\`\`\`text

[OK]

[WARNING]

[FAILED]

\`\`\`

At the end, the application provides:

\`\`\`text

Total PDFs

Successful

Warnings

Failed

\`\`\`

A text log is also saved with the output files.

**---**

**## 🛠️ How It Works**

\`\`\`text

Select PDFs / PDF URLs

        ↓

Enter New URL

        ↓

Upload Replacement Image

        ↓

Select Processing Options

        ↓

START BULK REPLACEMENT

        ↓

Validate PDF files

        ↓

Download PDFs if URLs were provided

        ↓

Replace hyperlinks

        ↓

Replace / Insert first-page image

        ↓

Optimize / Compress PDF

        ↓

Save processed PDF

        ↓

Generate processing log

        ↓

Create ZIP file

        ↓

Download results

\`\`\`

**---**

**## 🖥️ User Interface**

The application is built with a Gradio interface.

**### 1. PDF Files**

Upload multiple PDFs or upload a \`.txt\` file containing PDF URLs.

**### 2. New Link**

Enter the URL that should be used for PDF hyperlinks.

**### 3. Replacement Image**

Select the image that should be used for first-page replacement.

**### 4. Processing Options**

Choose:

\- Replace first-page image

\- Replace PDF hyperlinks

\- Preserve image aspect ratio

\- Keep original filenames

\- Insert image when no first-page image exists

\- Add whole-page first-page link

**### 4b. Compression**

Enable PDF compression and define the target size range.

**### 4c. Custom Output Names**

Optionally define:

\- Custom PDF filename

\- Custom ZIP filename

**### 5. Start Processing**

Click:

\`\`\`text

START BULK REPLACEMENT

\`\`\`

**### 6. Processing Log**

Monitor the processing status.

**### 7. Download Results**

Download the final ZIP file.

**---**

**## 💻 Technology Stack**

The project is built using Python and focused libraries.

**### Python**

Main programming language used by the application.

**### Gradio**

Used to build the web-based user interface.

Current configuration:

\`\`\`text

gradio==3.50.2

\`\`\`

**### PyMuPDF**

Used for reading, modifying, validating, and saving PDF documents.

**### Pillow**

Used for image validation, conversion, and image preparation.

**### Requests**

Used to download PDF files from URLs supplied through the \`.txt\` file.

**---**

**## 📦 Dependencies**

The project uses:

\`\`\`text

gradio==3.50.2

pymupdf

pillow

requests

\`\`\`

These dependencies are listed in:

\`\`\`text

requirements.txt

\`\`\`

**---**

**## 📂 Project Structure**

\`\`\`text

BulkPDFReplacer/

│

├── .gitignore

├── app.py

├── LICENSE

├── README.md

├── requirements.txt

│

└── .venv/

    └── ...

\`\`\`

**### \`app.py\`**

Contains the main application logic, including:

\- PDF validation

\- Image validation

\- PDF URL downloading

\- Image replacement

\- Hyperlink replacement

\- Whole-page link creation

\- PDF compression

\- Output filename generation

\- ZIP creation

\- Gradio interface

**### \`requirements.txt\`**

Contains the Python dependencies required to run the application.

**### \`.gitignore\`**

Prevents local/generated files such as the Python virtual environment, cache files, logs, and temporary output directories from being committed to Git.

**---**

**## ⚙️ Installation**

**### 1. Clone the Repository**

\`\`\`bash

git clone https\://github.com/Vaibhav-Chaurasiya/BulkPDFReplacer.git

\`\`\`

Move into the project directory:

\`\`\`bash

cd BulkPDFReplacer

\`\`\`

**### 2. Create a Virtual Environment**

On Windows:

\`\`\`powershell

python -m venv .venv

\`\`\`

Activate it:

\`\`\`powershell

.\\.venv\Scripts\Activate.ps1

\`\`\`

**### 3. Install Dependencies**

\`\`\`powershell

python -m pip install -r requirements.txt

\`\`\`

**---**

**## ▶️ Run the Application**

Start the application with:

\`\`\`powershell

python app.py

\`\`\`

The application starts the Gradio interface.

Open the URL shown in the terminal in your browser.

**---**

**## 🧪 Basic Usage**

**### Example 1 — Replace Links**

1\. Upload one or more PDFs.

2\. Enter the new URL.

3\. Enable **\*\*Replace PDF hyperlinks\*\***.

4\. Choose whether all existing links should be replaced.

5\. Click **\*\*START BULK REPLACEMENT\*\***.

6\. Download the generated ZIP.

**### Example 2 — Replace First-Page Images**

1\. Upload multiple PDFs.

2\. Upload a replacement image.

3\. Enable **\*\*Replace first-page image\*\***.

4\. Select **\*\*Largest image\*\*** or **\*\*First image\*\***.

5\. Enable **\*\*Preserve image aspect ratio\*\*** if required.

6\. Start processing.

7\. Download the output ZIP.

**### Example 3 — Process PDFs From URLs**

Create a file such as:

\`\`\`text

pdf_links.txt

\`\`\`

Add one PDF URL per line:

\`\`\`text

https\://example.com/file1.pdf

https\://example.com/file2.pdf

https\://example.com/file3.pdf

\`\`\`

Upload this \`.txt\` file.

The application will:

\`\`\`text

Read URLs

   ↓

Download PDFs

   ↓

Validate PDFs

   ↓

Process PDFs

   ↓

Save outputs

   ↓

Create ZIP

\`\`\`

**---**

**## 🔐 Original Files Are Not Modified**

The application creates separate output files for processed documents rather than intentionally overwriting the source PDFs.

This helps keep the original files available as a backup/reference.

**---**

**## 🛡️ PDF Validation**

Before processing, the application checks whether the input PDF is usable.

It checks for conditions such as:

\- File existence

\- \`.pdf\` extension

\- Corrupt or unreadable PDFs

\- Password-protected PDFs

\- PDFs with zero pages

Invalid files are reported in the processing log.

**---**

**## 🖼️ Image Validation**

Before using a replacement image, the application checks:

\- Whether the file exists

\- Whether the extension is supported

\- Whether the image can be opened correctly

Supported formats:

\`\`\`text

.png

.jpg

.jpeg

.webp

\`\`\`

**---**

**## ⚠️ Processing Status**

**### \`[OK]\`**

The PDF was processed successfully.

**### \`[WARNING]\`**

The PDF was processed, but something needs attention.

Examples:

\- No existing hyperlink was found

\- No image was found

\- Compression could not reach the requested maximum size

\- A fallback image replacement method was required

**### \`[FAILED]\`**

The PDF could not be processed successfully.

The log includes the reason for the failure whenever available.

**---**

**## 📉 Compression Behavior**

Compression works progressively.

The application first performs PDF optimization.

If the PDF is still above the maximum target size, embedded images are recompressed using progressively lower JPEG quality settings.

The application does not add meaningless data simply to increase a file to the minimum size.

**---**

**## 📋 Output**

Example output package:

\`\`\`text

bulk_pdf_replacer_output.zip

│

├── document1.pdf

├── document2.pdf

├── document3.pdf

└── pdf_replacement_log.txt

\`\`\`

The log contains:

\- Processing results

\- Status of individual PDFs

\- Warnings

\- Failures

\- Total number of PDFs

\- Successful count

\- Warning count

\- Failed count

\- Processing timestamp

**---**

**## 🧑‍💻 Development**

The application is intentionally kept as a single Python application so it is easy to understand and modify.

The main areas of the code are organized around:

\`\`\`text

Validation

    ↓

Download Helpers

    ↓

Image Helpers

    ↓

PDF Processing

    ↓

Compression

    ↓

Output Naming

    ↓

Gradio UI

\`\`\`

**---**

**## 🔧 Possible Future Improvements**

Possible future improvements include:

\- More PDF editing operations

\- Advanced hyperlink selection

\- More image placement controls

\- Additional compression strategies

\- Better batch reporting

\- Drag-and-drop workflow improvements

\- More detailed error reporting

\- Background processing for very large batches

\- Additional output formats

\- More customizable page/image positioning

**---**

**## 📜 License**

This project includes a \`LICENSE\` file in the repository.

Please refer to that file for the exact license terms.

**---**

**## 👨‍💻 Author**

**\*\*Vaibhav Chaurasiya\*\***

GitHub:

https\://github.com/Vaibhav-Chaurasiya

**---**

**## ⭐ Contributing**

If you find a bug, have an improvement idea, or want to extend the project, feel free to create an issue or submit a pull request.

Before submitting changes, please make sure that:

1\. The application still starts correctly.

2\. Existing PDF processing functionality is not unintentionally broken.

3\. New dependencies are added to \`requirements.txt\` when required.

4\. Temporary files and virtual environments are not committed.

5\. Changes are tested with more than one PDF where possible.

**---**

**## 📌 Important Notes**

\- Keep a backup of important PDFs before performing large batch operations.

\- PDF files can have different internal structures, so results may vary between documents.

\- Password-protected PDFs that cannot be authenticated are rejected.

\- Compression can reduce image quality when aggressive size reduction is required.

\- The original input PDFs are not intentionally overwritten.

\- \`.venv\` should remain outside Git tracking.

**---**

**## ❤️ Project Goal**

The goal of **\*\*Bulk PDF Link & Image Replacer\*\*** is simple:

\> **\*\*Take a repetitive PDF editing task and turn it into a simple bulk workflow.\*\***

Instead of spending time opening, editing, saving, and closing PDFs individually, the application brings common operations into one interface.

Upload your files, select what needs to change, start the process, and download the results.

**---**

**## 🚀 Quick Start**

For anyone who just wants to run the project:

\`\`\`powershell

git clone https\://github.com/Vaibhav-Chaurasiya/BulkPDFReplacer.git

cd BulkPDFReplacer

python -m venv .venv

.\\.venv\Scripts\Activate.ps1

python -m pip install -r requirements.txt

python app.py

\`\`\`

Then open the Gradio URL shown in the terminal.

**---**

**\*\*Bulk PDF Link & Image Replacer\*\***  

Built to make repetitive PDF editing faster, simpler, and easier to manage.