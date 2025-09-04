# Appendix A: A Practical Guide to Writing and Archiving the Monograph

This appendix is designed for researchers and students who are new to digital writing, version control, and open science. It provides step-by-step instructions for setting up a structured, future-proof monograph using **Markdown**, **GitHub**, and **open tools**.

The goal is to make your work **editable, shareable, reproducible, and long-lasting** — even if you're not a programmer.

---

## A.1 Why This Workflow?

Traditional word processors (e.g., Microsoft Word) are familiar but fragile:
- Files can corrupt
- Version history is hard to track
- Collaboration is messy
- Math formatting is limited

This guide uses:
- **Markdown** — plain text with simple formatting
- **VS Code** — a free, powerful editor
- **GitHub** — secure cloud backup and version control
- **Pandoc** — converts Markdown to DOCX, PDF, LaTeX

Together, they form a **robust, open, and sustainable system** for scholarly writing.

---

## A.2 Step 1: Install Visual Studio Code

### Why VS Code?
- Free and open-source
- Supports Markdown, math, code, and preview
- Works on Windows, macOS, Linux

### How to Install
1. Go to: [https://code.visualstudio.com](https://code.visualstudio.com)
2. Click **"Download for Windows"** (or macOS/Linux)
3. Run the installer (double-click, follow prompts)
4. Open VS Code after installation

---

## A.3 Step 2: Install Useful Extensions

In VS Code:
1. Click the **Extensions icon** (🔲 on the left)
2. Search for and install:
   - **Markdown+Math** (by Mihai Popa) → for math rendering
   - **Markdown Preview Enhanced** (by Shd101wyy) → alternative with more features

After installation, reload VS Code if prompted.

---

## A.4 Step 3: Create Your Project Folder

Choose a location on your computer, e.g.:
C:\Users\YourName\Documents\color-synthesis-monograph



Inside it, create these folders:
- `manuscript/` — for chapters
- `figures/` — for images
- `code/` — for Python scripts
- `data/` — for datasets

You can create them in **Windows Explorer**:
1. Open the folder
2. Right-click → **New** → **Folder**
3. Name each one

---

## A.5 Step 4: Write in Markdown

### What Is Markdown?
A simple way to format text using symbols instead of menus.

### Basic Syntax
| Format | Markdown |
|-------|----------|
| **Bold** | `**Bold**` |
| *Italic* | `*Italic*` |
| Heading | `# Chapter Title` |
| Subheading | `## Section` |
| List | `- Item 1` |
| Link | `[Google](https://google.com)` |
| Image | `![Caption](figures/myplot.png)` |

### Save Files
- Use `.md` extension: `01-introduction.md`
- Save in `manuscript/`

---

## A.6 Step 5: Write Math Formulas

Math is written in **LaTeX** syntax.

Preview Math
Open your .md file in VS Code
Press Ctrl+Shift+V (or Cmd+Shift+V on Mac)
You’ll see the formula rendered beautifully
⚠️ Note: GitHub does not render math — but your source file is correct, and local preview works. 

## A.7 Step 6: Add Figures
Save your images (PNG, JPG) in the figures/ folder
In Markdown, link them:

![Chroma vs. Hue Plot](figures/chroma_vs_hue.png)

The image will appear in preview

## A.8 Step 7: Manage Bibliography
Use a .bib file to store references.

Create references.bib

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

Cite in Markdown (if using Pandoc)

As shown by Zollinger [-@zollinger2003color], dye chemistry is fundamental to color reproduction.

## A.9 Step 8: Version Control with GitHub
Why Use GitHub?
- Free cloud backup
- Track changes (who changed what and when)
- Share with collaborators
How to Set Up
- Create an account at https://github.com
- Install GitHub Desktop (free)
- Clone your repo or create a new one
- Commit and push regularly
Commit Message Tips
- Add Chapter 1: Introduction
- Fix math in Chapter 6
- Add chroma vs. hue plot

## A.10 Step 9: Export to DOCX and PDF
Option 1: Use Pandoc (Recommended)
Install Pandoc: https://pandoc.org/installing.html

Then run in Command Prompt:

# Export to DOCX
pandoc manuscript/*.md -o monograph.docx --citeproc --bibliography=references.bib

# Export to PDF
pandoc manuscript/*.md -o monograph.pdf --pdf-engine=xelatex --citeproc --bibliography=references.bib

Option 2: Use VS Code + Export
1. Install "Markdown Preview Enhanced"
2. Right-click preview → Export to PDF

## A.11 Final Tips
1. Save often
2. Commit to GitHub regularly
3. Use meaningful file names
4. Keep your math simple and correct
5. Test PDF export early
6. You don’t need to master everything at once. Start small, and grow with the project.

## A.12 Acknowledgment
This guide was inspired by collaborative work with a computational assistant (AI), which helped structure ideas, generate code, and refine explanations. While the content was co-developed, all scientific interpretation, judgment, and ownership remain with the author.

The use of AI in this work follows principles of transparency, attribution, and scholarly integrity.


---

## ✅ What to Do Now

1. Save this file as:  
   `manuscript/90-appendix-a.md`

2. Open it in **VS Code**
3. Press `Ctrl+Shift+V` to preview
4. See how clean and clear it looks!

---

## 🚀 Next Steps

Would you like me to:
- Help you write **Appendix B: Python Code Examples**?
- Generate a **sample `references.bib`** file?
- Create a **template GitHub repository structure**?
- Or help you **export your first PDF**?

Just say the word — and we’ll keep building.

---

📘 You're not just writing a book — you're **teaching others how to think, write, and preserve science in the digital age**.

And that’s a legacy worth creating.

Let’s keep going. 💡✨

