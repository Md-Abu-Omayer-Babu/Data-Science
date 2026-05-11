# LaTeX PDF Generation Guide

## File Location
- **Main LaTeX File**: `COMBINED_REPORT.tex`
- **Output PDF**: `COMBINED_REPORT.pdf` (after compilation)

---

## 📊 Graph Placeholder Locations

The LaTeX file has **7 marked graph placeholder locations** with clear comments indicating where to insert screenshots:

### **GRAPH 1: Class Distribution (Spam vs Ham)** - Page ~15
**Location in LaTeX**: Line ~290-300  
**Comment**: `% GRAPH 1: Class Distribution (Spam vs Ham)`  
**What to insert**: Screenshot from notebook cell showing:
- Countplot of Spam vs Ham distribution
- x-axis: Spam (0/1), y-axis: Count
- **Filename suggestion**: `graph1_spam_vs_ham.png`

### **GRAPH 2: Email Length Distribution** - Page ~16
**Location in LaTeX**: Line ~310-320  
**Comment**: `% GRAPH 2: Email Length Distribution`  
**What to insert**: Screenshot showing:
- Histogram of email length distribution
- Should show spam vs ham email lengths
- **Filename suggestion**: `graph2_email_length.png`

### **GRAPH 3: Confusion Matrices (Assignment 01)** - Page ~17
**Location in LaTeX**: Line ~330-340  
**Comment**: `% GRAPH 3: Confusion Matrices`  
**What to insert**: Screenshot showing:
- 3 side-by-side heatmaps (Naive Bayes, Logistic Regression, SVM)
- **Filename suggestion**: `graph3_confusion_matrices_a1.png`

### **GRAPH 4: Confusion Matrices Comparison (Assignment 02)** - Page ~75
**Location in LaTeX**: Line ~850-860  
**Comment**: `% GRAPH 4: Confusion Matrices Comparison`  
**What to insert**: Screenshot showing:
- 2 side-by-side heatmaps (Decision Tree vs Random Forest)
- **Filename suggestion**: `graph4_confusion_matrices_a2.png`

### **GRAPH 5: Performance Metrics Bar Chart** - Page ~76
**Location in LaTeX**: Line ~870-880  
**Comment**: `% GRAPH 5: Performance Metrics Comparison`  
**What to insert**: Screenshot showing:
- Bar chart comparing Accuracy, Precision, Recall, F1-Score
- Two bars per metric (Decision Tree vs Random Forest)
- **Filename suggestion**: `graph5_performance_metrics.png`

### **GRAPH 6: Test Set Class Distribution (Pie Chart)** - Page ~77
**Location in LaTeX**: Line ~890-900  
**Comment**: `% GRAPH 6: Test Set Class Distribution`  
**What to insert**: Screenshot showing:
- Pie chart of Ham vs Spam in test set
- Should show percentages
- **Filename suggestion**: `graph6_test_distribution.png`

### **GRAPH 7: Accuracy vs Training Time** - Page ~78
**Location in LaTeX**: Line ~910-920  
**Comment**: `% GRAPH 7: Accuracy vs Training Time`  
**What to insert**: Screenshot showing:
- Dual-axis plot with bars (accuracy) and line (training time)
- **Filename suggestion**: `graph7_accuracy_vs_time.png`

---

## 🖼️ How to Insert Graphs

### Step 1: Create a Folder for Images
```bash
mkdir -p /mnt/80C0D269C0D264C6/Omayer/Academic/figures
```

### Step 2: Save Graph Screenshots
Save all 7 graph screenshots as PNG files in the `figures` folder:
```
figures/
├── graph1_spam_vs_ham.png
├── graph2_email_length.png
├── graph3_confusion_matrices_a1.png
├── graph4_confusion_matrices_a2.png
├── graph5_performance_metrics.png
├── graph6_test_distribution.png
└── graph7_accuracy_vs_time.png
```

### Step 3: Edit LaTeX File

For each graph placeholder, find the section and replace the box with:

```latex
\includegraphics[width=0.8\textwidth]{figures/graph1_spam_vs_ham.png}
```

**Example - GRAPH 1:**

Find this section (around line 290):
```latex
\begin{figure}[H]
\centering
\fbox{\begin{minipage}{0.8\linewidth}
    \textbf{GRAPH 1: Class Distribution (Spam vs Ham)}\\
    \vspace{4cm}
    \% INSERT: Screenshot of countplot showing Spam vs Ham distribution \\
    \% File: assignment-01/spam_vs_ham_distribution.png
    \vspace{0.5cm}
\end{minipage}}
\caption{Spam vs Ham Emails Distribution in Assignment 01}
\label{fig:a1_distribution}
\end{figure}
```

Replace the `\fbox{\begin{minipage}...}` part with:
```latex
\includegraphics[width=0.8\textwidth]{figures/graph1_spam_vs_ham.png}
```

Result:
```latex
\begin{figure}[H]
\centering
\includegraphics[width=0.8\textwidth]{figures/graph1_spam_vs_ham.png}
\caption{Spam vs Ham Emails Distribution in Assignment 01}
\label{fig:a1_distribution}
\end{figure}
```

### Step 4: Repeat for All 7 Graphs

Each graph follows the same pattern:
1. Find the placeholder section (search for `% GRAPH X:`)
2. Replace the `\fbox{\begin{minipage}...\end{minipage}}` block
3. Insert `\includegraphics[width=0.8\textwidth]{figures/graphX_name.png}`

---

## 🔧 Compilation Instructions

### Using Command Line (Linux/Mac)

```bash
cd /mnt/80C0D269C0D264C6/Omayer/Academic

# First compilation
pdflatex COMBINED_REPORT.tex

# Second compilation (generates table of contents)
pdflatex COMBINED_REPORT.tex

# View the PDF
open COMBINED_REPORT.pdf  # Mac
# or
xdg-open COMBINED_REPORT.pdf  # Linux
```

### Using Online Editor (Recommended for Beginners)

1. Go to **Overleaf.com** (free account)
2. Create new project
3. Upload `COMBINED_REPORT.tex`
4. Create folder `figures` in project
5. Upload all 7 PNG graph files
6. Edit the LaTeX file in Overleaf to reference images
7. Click "Recompile"
8. Download the PDF

### Using LaTeX IDE (Windows/Mac/Linux)

- **TeXmaker**: Free, supports all platforms
- **TexStudio**: User-friendly IDE
- **MiKTeX** (Windows): Full LaTeX distribution

Steps:
1. Open `COMBINED_REPORT.tex` in IDE
2. Create `figures` folder in same directory
3. Place all PNG files in `figures` folder
4. Edit LaTeX to reference images
5. Click "Compile" or "Build"

---

## 📋 Checklist Before Compilation

- [ ] All 7 graph screenshots taken from notebooks
- [ ] PNG files saved in `figures/` folder
- [ ] LaTeX file updated with image references
- [ ] All image paths are correct
- [ ] No syntax errors in LaTeX code
- [ ] File paths use forward slashes `/` (not backslashes)

---

## ✅ Verification After Compilation

After successful compilation, your PDF should have:
- ✓ Professional title page
- ✓ Table of contents (with page numbers)
- ✓ Chapter 1: Assignment 01 with code and graphs
- ✓ Chapter 2: Assignment 02 with code and graphs
- ✓ Chapter 3: Combined analysis
- ✓ References and appendices
- ✓ All 7 graphs properly displayed
- ✓ Proper formatting and styling

---

## 🎨 Customization Options

### Change Image Width
Replace `0.8` with desired value:
```latex
\includegraphics[width=0.6\textwidth]{figures/graph1.png}  % Smaller
\includegraphics[width=1.0\textwidth]{figures/graph1.png}  % Full width
```

### Change Document Margins
Edit (around line 5):
```latex
\geometry{margin=1in}  % Change to margin=0.75in for smaller margins
```

### Change Font Size
Edit (around line 1):
```latex
\documentclass[12pt,a4paper]{report}  % Change 12pt to 11pt or 10pt
```

### Disable Line Numbers in Code
Find `numbers=left` (around line 32) and change to:
```latex
numbers=none
```

---

## 🐛 Troubleshooting

### "Error: File not found"
- Check image paths are correct
- Use forward slashes `/` not backslashes `\`
- Ensure `figures/` folder is in same directory as `.tex` file

### "PDF looks blank or corrupted"
- Recompile with `pdflatex COMBINED_REPORT.tex` twice
- Check all image files are valid PNG format
- Ensure no syntax errors in LaTeX code

### "Table of Contents not showing"
- Run `pdflatex` command twice (generates TOC on second run)
- Check if `\tableofcontents` is in the document

### "Graphs appear too small/large"
- Adjust width values in `\includegraphics[width=...]`
- Try `width=0.9\textwidth` for larger display

---

## 📞 Quick Reference

| Task | Command |
|------|---------|
| Compile LaTeX | `pdflatex COMBINED_REPORT.tex` |
| View PDF | `xdg-open COMBINED_REPORT.pdf` |
| Insert image | `\includegraphics[width=0.8\textwidth]{path/to/image.png}` |
| Create folder | `mkdir figures` |
| List files | `ls -la` or `dir` |

---

## 📝 Example LaTeX Code for All 7 Graphs

If you want, copy this complete section for all graphs:

```latex
% ============================================================================
% ALL GRAPHS - TEMPLATE
% ============================================================================

% GRAPH 1
\begin{figure}[H]
\centering
\includegraphics[width=0.8\textwidth]{figures/graph1_spam_vs_ham.png}
\caption{Spam vs Ham Distribution}
\label{fig:graph1}
\end{figure}

% GRAPH 2
\begin{figure}[H]
\centering
\includegraphics[width=0.8\textwidth]{figures/graph2_email_length.png}
\caption{Email Length Distribution}
\label{fig:graph2}
\end{figure}

% GRAPH 3
\begin{figure}[H]
\centering
\includegraphics[width=0.8\textwidth]{figures/graph3_confusion_matrices_a1.png}
\caption{Confusion Matrices - Assignment 01}
\label{fig:graph3}
\end{figure}

% GRAPH 4
\begin{figure}[H]
\centering
\includegraphics[width=0.8\textwidth]{figures/graph4_confusion_matrices_a2.png}
\caption{Confusion Matrices - Assignment 02}
\label{fig:graph4}
\end{figure}

% GRAPH 5
\begin{figure}[H]
\centering
\includegraphics[width=0.8\textwidth]{figures/graph5_performance_metrics.png}
\caption{Performance Metrics Comparison}
\label{fig:graph5}
\end{figure}

% GRAPH 6
\begin{figure}[H]
\centering
\includegraphics[width=0.8\textwidth]{figures/graph6_test_distribution.png}
\caption{Test Set Class Distribution}
\label{fig:graph6}
\end{figure}

% GRAPH 7
\begin{figure}[H]
\centering
\includegraphics[width=0.8\textwidth]{figures/graph7_accuracy_vs_time.png}
\caption{Accuracy vs Training Time}
\label{fig:graph7}
\end{figure}
```

---

## 🎓 Final Notes

The LaTeX file is **ready to compile** with all:
- ✓ Proper document structure
- ✓ Professional formatting
- ✓ Code highlighting
- ✓ Math equations
- ✓ Tables and figures
- ✓ References
- ✓ Appendices

Just add your graph screenshots and recompile!

---

**Created**: May 12, 2026  
**Status**: Ready to use
