# Appendix B: Using Citavi for Bibliography Management with Markdown

This appendix explains how to use **Citavi** — a powerful reference management tool — in combination with **Markdown** and **Pandoc** to create a **fully integrated, publication-ready monograph** with automatic citations and bibliography.

By following this guide, you can:
- Export references from Citavi in BibTeX format
- Cite them in your Markdown files
- Automatically generate a formatted bibliography when exporting to PDF or DOCX

This workflow is ideal for long-form writing, such as books, theses, or reviews.

---

## B.1 Why Use Citavi with Markdown?

Citavi excels at:
- Organizing thousands of references
- Managing PDFs and notes
- Generating citations and bibliographies

When combined with **Markdown** and **Pandoc**, it becomes part of a **modern, open, and reproducible writing system** that:
- Keeps your content in plain text (future-proof)
- Automates citation formatting
- Supports export to PDF, DOCX, HTML, and more

---

## B.2 Step 1: Export References from Citavi as BibTeX

1. Open your project in **Citavi**
2. Select the references you want to include (or select all)
3. Go to:  
   **File → Export → Export to Text File**
4. In the export dialog:
   - Choose format: **BibTeX (*.bib)**
   - Select fields to export: Title, Author, Year, Journal, etc.
   - Click **OK**
5. Save the file as:  
   `references.bib`  
   in the root of your project folder

> ✅ Example location:  
> `color-synthesis-monograph/references.bib`

---

## B.3 Step 2: Verify the BibTeX File

Open `references.bib` in **VS Code** to check its content. It should look like this:

```bibtex
@book{zollinger2003color,
  title={Color Chemistry: Syntheses, Properties, and Applications of Synthetic Dyes and Pigments},
  author={Zollinger, Heinz},
  year={2003},
  publisher={Wiley-VCH}
}

@article{luo2001development,
  title={The development of the CIE 2000 colour-difference formula},
  author={Luo, Ming Ronnier and Cui, Guihua and Rigg, B},
  journal={Color Research & Application},
  volume={26},
  number={5},
  pages={340--350},
  year={2001}
}
```

Each entry has a citation key (e.g., zollinger2003color) — you’ll use this to cite in Markdown.

## B.4 Step 3: Cite in Markdown Using Pandoc Syntax
In your .md files (e.g., 01-introduction.md, 06-iso-hue-scales.md), cite references using Pandoc’s citation syntax:

| Citation Style | Markdown Syntax                                          |
|----------------|----------------------------------------------------------|
| Parenthetical  | [@zollinger2003color]" → (Zollinger 2003"                |
| Narrative      | [-@zollinger2003color] → Zollinger (2003)                |
| With page      | [@zollinger2003color, p. 45]" → (Zollinger, 2003, p. 45) |


Example in Context
As shown by Zollinger [-@zollinger2003color], dye chemistry is fundamental to color reproduction.

More recent work has improved color difference formulas [@luo2001development].

## B.5 Step 4: Export to PDF or DOCX with Pandoc
Once you’ve written your chapters and cited your sources, use Pandoc to generate a final document with fully formatted citations and bibliography.

Install Pandoc (if not done)

pandoc manuscript/*.md -o monograph.docx --citeproc --bibliography=references.bib

This will:

Combine all .md files
Format citations
Generate a References section at the end
Export to PDF (with LaTeX)

pandoc manuscript/*.md -o monograph.pdf --citeproc --bibliography=references.bib --pdf-engine=xelatex

## B.6 Step 5: (Optional) Customize Citation Style
By default, Pandoc uses Chicago author-date. To change the style:

Download a Citation Style Language (CSL) file:
Go to: https://www.zotero.org/styles
Search for your preferred style (e.g., APA, IEEE, Nature)
Download the .csl file
Save it in your project, e.g.: apa.csl
Add --csl=apa.csl to your Pandoc command:

## B.7 Best Practices
| Practice                       | Recommendation                                                 |
|--------------------------------|----------------------------------------------------------------|
| Update regularly               | Re-export references.bib when you add new references in Citavi |
| Use meaningful citation keys   | Citavi uses AuthorYear format — keep it                        |
| Test early                     | Generate a test PDF with one citation to verify formatting     |
| Keep `.bib` in version control | Commit to GitHub so your team can access it                    |

## B.8 Troubleshooting
| Issue                            | Solution                                                             |
|----------------------------------|----------------------------------------------------------------------|
| "Citation not found"             | Check spelling of citation key in .md and .bib                       |
| No bibliography generated        | Make sure --citeproc --bibliography=references.bib is in the command |
| Math not rendering in PDF        | Use --pdf-engine=xelatex and ensure LaTeX is installed               |
| Special characters (é, ü) broken | Save .md and .bib in UTF-8 encoding                                  |


## B.9 Final Thoughts
You’re not just writing — you’re building a professional, scholarly publication system.

By combining:

Citavi for reference management
Markdown for clean, structured writing
Pandoc for automated formatting
You’ve created a robust, scalable, and future-proof workflow that can grow with your research.

Keep going — and let your ideas shine.

📘✨