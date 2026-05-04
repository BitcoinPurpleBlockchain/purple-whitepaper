# BitcoinPurple Whitepaper

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

Source files for the official BitcoinPurple (BTCP) whitepaper, written in LaTeX.

- **Website:** [bitcoinpurpleblockchain.com](https://bitcoinpurpleblockchain.com/)
- **Explorer:** [bitcoinpurple-explorer.online](https://bitcoinpurple-explorer.online/)
- **Community:** [Telegram](https://t.me/+o3I0A1q1W29mMmQ0)

---

## Repository structure

```
whitepaper/
├── src/
│   ├── whitepaper.tex      # LaTeX source
│   └── icon.png            # Official BTCP logo
├── whitepaper.pdf          # Latest compiled PDF
└── .gitignore
```

---

## Build the PDF

### Requirements

You need a LaTeX distribution with the following packages:

**Debian / Ubuntu / Raspberry Pi OS:**
```bash
sudo apt install texlive-latex-extra texlive-fonts-recommended
```

**macOS (Homebrew):**
```bash
brew install --cask mactex
```

**Windows:** install [MiKTeX](https://miktex.org/) or [TeX Live](https://tug.org/texlive/).

Packages used by the document (all included in the distributions above):

`geometry`, `fancyhdr`, `amsmath`, `xcolor`, `graphicx`, `booktabs`, `array`,
`longtable`, `tabularx`, `multirow`, `listings`, `courier`, `hyperref`,
`titlesec`, `enumitem`, `parskip`, `seqsplit`, `microtype`, `lmodern`

---

### Compile

From the `src/` directory, run `pdflatex` **twice** — the first pass generates the table of contents, the second resolves all references:

```bash
cd src
pdflatex whitepaper.tex
pdflatex whitepaper.tex
```

Output: `src/whitepaper.pdf` — copy it to the repo root to update the distributed PDF:

```bash
cp whitepaper.pdf ../whitepaper.pdf
```

---

### One-liner (clean build + move PDF to root)

```bash
cd src && pdflatex whitepaper.tex && pdflatex whitepaper.tex && cp whitepaper.pdf ../whitepaper.pdf && rm -f whitepaper.aux whitepaper.log whitepaper.out whitepaper.toc
```

---

## Contributing

1. **Technical corrections** — open a pull request with your changes to `src/whitepaper.tex`. Keep edits focused; one topic per PR.

2. **Wording / translations** — open a pull request with your changes to `src/whitepaper.tex`. Keep edits focused; one topic per PR.

3. **Do not edit the PDF directly** — only `src/whitepaper.tex` is the source of truth.

4. **Do not commit build artifacts** — `*.aux`, `*.log`, `*.out`, `*.toc` are in `.gitignore` and must not be committed.

---

## Authors

| Name | Role |
|---|---|
| Alym Wehrli | Founder |
| Davide Grilli | Developer & Maintainer |
| Maurito83 | Community Manager |
