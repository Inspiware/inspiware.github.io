# How to Convert TeX Energy Sector Brief to PDF

## File to Convert
`TeX_Energy_Sector_Brief_Presentation.md`

This is a presentation-ready version of the Energy Sector Brief with:
- ✅ No Calendly link (removed)
- ✅ Professional formatting optimized for PDF
- ✅ Clear section breaks with horizontal rules
- ✅ Tables and formatting suitable for printing
- ✅ Contact information at the end

---

## Method 1: Using Microsoft Word (Recommended)

### Steps:
1. **Open the Markdown file** in Visual Studio Code or any text editor
2. **Copy all content** (Ctrl+A, Ctrl+C)
3. **Open Microsoft Word**
4. **Paste** the content (Ctrl+V)
5. **Apply formatting**:
   - Set font to Calibri or Arial (11-12pt for body, 16-24pt for headings)
   - Apply heading styles (Heading 1, Heading 2, etc.)
   - Format tables using Word's table styles
   - Add page breaks between major sections
   - Adjust margins (0.75" or 1" all around)
6. **Save as PDF**:
   - File → Save As → PDF
   - Or File → Export → Create PDF/XPS

**Result**: Professional PDF with proper formatting

---

## Method 2: Using Pandoc (Command Line)

### Prerequisites:
Install Pandoc: https://pandoc.org/installing.html

### Command:
```powershell
cd C:\LocalWorkFolder\Inspiware\inspiware.github.io\sales
pandoc TeX_Energy_Sector_Brief_Presentation.md -o TeX_Energy_Sector_Brief.pdf --pdf-engine=xelatex -V geometry:margin=1in
```

### With Custom Styling:
```powershell
pandoc TeX_Energy_Sector_Brief_Presentation.md -o TeX_Energy_Sector_Brief.pdf --pdf-engine=xelatex -V geometry:margin=1in -V fontsize=11pt -V documentclass=article
```

**Result**: Clean PDF with basic formatting

---

## Method 3: Using Online Markdown to PDF Converter

### Recommended Services:
1. **Markdown to PDF** - https://www.markdowntopdf.com/
2. **Dillinger** - https://dillinger.io/ (export to PDF)
3. **StackEdit** - https://stackedit.io/ (export to PDF)

### Steps:
1. Open the online converter
2. Copy/paste the markdown content or upload the file
3. Click "Convert to PDF" or "Export to PDF"
4. Download the generated PDF

**Result**: Quick PDF conversion with basic formatting

---

## Method 4: Using Visual Studio Code Extension

### Prerequisites:
Install VS Code extension: "Markdown PDF" by yzane

### Steps:
1. Open `TeX_Energy_Sector_Brief_Presentation.md` in VS Code
2. Right-click in the editor
3. Select "Markdown PDF: Export (pdf)"
4. PDF will be generated in the same folder

**Result**: PDF with VS Code's markdown styling

---

## Method 5: Using Google Docs

### Steps:
1. **Open Google Docs** (docs.google.com)
2. **Create new document**
3. **Copy/paste** the markdown content
4. **Apply formatting**:
   - Format headings (use Heading 1, Heading 2, etc.)
   - Format tables
   - Add page breaks
5. **Download as PDF**:
   - File → Download → PDF Document (.pdf)

**Result**: Professional PDF with Google Docs formatting

---

## Recommended Approach for Best Results

### For Professional Presentation:

1. **Use Microsoft Word** (Method 1)
2. **Apply these formatting guidelines**:
   - **Title Page**: 
     - Title: "TeX Platform for Energy & Utilities" (24pt, bold)
     - Subtitle: "AI-Powered Enterprise Integration for the Energy Transition" (16pt)
     - Inspiware logo (if available)
     - Contact info at bottom
   
   - **Body Pages**:
     - Headings: 16pt bold (dark blue #0078d4)
     - Subheadings: 14pt bold
     - Body text: 11pt Calibri or Arial
     - Tables: Use "Grid Table 5 Dark - Accent 1" style
     - Bullet points: Use checkmarks (✅) and icons where shown
   
   - **Page Layout**:
     - Margins: 1" all around
     - Header: "TeX Platform for Energy & Utilities" (right-aligned, 9pt)
     - Footer: Page numbers (centered, 9pt)
     - Page breaks before major sections
   
   - **Colors**:
     - Primary: #0078d4 (TeX blue)
     - Secondary: #00bcf2 (TeX cyan)
     - Accent: #f97316 (orange for highlights)
     - Text: #1a1a1a (dark gray)

3. **Review and polish**:
   - Check all tables render correctly
   - Ensure no orphaned headings at page breaks
   - Verify all icons/emojis display properly
   - Proofread for consistency

4. **Save as PDF** with these settings:
   - Standard quality (not minimum)
   - Include document properties
   - ISO 19005-1 compliant (PDF/A) for archival

---

## Quick PowerShell Script (Requires Pandoc)

Save this as `convert_to_pdf.ps1` in the sales folder:

```powershell
# Convert TeX Energy Sector Brief to PDF
$inputFile = "TeX_Energy_Sector_Brief_Presentation.md"
$outputFile = "TeX_Energy_Sector_Brief.pdf"

# Check if Pandoc is installed
if (!(Get-Command pandoc -ErrorAction SilentlyContinue)) {
    Write-Host "Error: Pandoc is not installed. Please install from https://pandoc.org/installing.html" -ForegroundColor Red
    exit 1
}

# Convert to PDF
Write-Host "Converting $inputFile to PDF..." -ForegroundColor Green
pandoc $inputFile -o $outputFile --pdf-engine=xelatex -V geometry:margin=1in -V fontsize=11pt -V documentclass=article

if (Test-Path $outputFile) {
    Write-Host "Success! PDF created: $outputFile" -ForegroundColor Green
    Start-Process $outputFile
} else {
    Write-Host "Error: PDF conversion failed" -ForegroundColor Red
}
```

Run with: `.\convert_to_pdf.ps1`

---

## File Comparison

| **File** | **Purpose** | **Calendly Link** | **Format** |
|----------|-------------|-------------------|------------|
| `TeX_Energy_Sector_Brief.md` | Original detailed brief | ✅ Included | Markdown |
| `TeX_Energy_Sector_Brief_Presentation.md` | PDF-ready version | ❌ Removed | Markdown |
| `TeX_Energy_Sector_Brief.pdf` | Final presentation | ❌ Not included | PDF (to be created) |

---

## Tips for Best PDF Output

1. **Remove emoji if they don't render well** - Replace with text equivalents
2. **Simplify tables** - Ensure they fit on one page width
3. **Add page breaks** - Before major sections for better flow
4. **Use consistent spacing** - 1.15 or 1.5 line spacing for readability
5. **Test print** - Print one page to verify formatting before finalizing

---

## Need Help?

Contact Inspiware team:
- Email: sales@inspiware.co.uk
- Phone: +44 (0) 742 414 4207

---

**Recommended**: Use Method 1 (Microsoft Word) for the most professional results with full control over formatting and styling.

