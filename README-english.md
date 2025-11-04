
<h1 align="center">SmartAspas</h1>

<p align="center">
  <img src="https://img.shields.io/badge/license-MIT-blue?style=for-the-badge" alt="License">
  <img src="https://img.shields.io/github/repo-size/Boudenzin/SmartAspas?style=for-the-badge" alt="Repository Size">
  <img src="https://img.shields.io/badge/LaTeX-3D6117?style=for-the-badge&logo=latex&logoColor=white" alt="LaTeX">
</p>

**SmartAspas** is a LaTeX package that automates the use of typographer's quotation marks (smart quotes). Instead of manually typing ``'' or `\enquote{}`, simply type `"nested 'like this' here"` and the package automatically converts it to **"double smart quotes"** and **'single smart quotes'**, respecting the document's language.

---

## ✨ Features

- **Automatic Quotes**: converts `"` into typographer's quotation marks.
- **Multilingual Support**: Portuguese, English, and French (or auto-detection via `babel`/`polyglossia`).
- **Correct Nesting**: secondary quotes inside primary ones.
- **Local Control**: `smartaspasoff` and `smartaspason` environments turn the feature on/off within blocks without leaking state.
- **Compatibility**: integrates with [`csquotes`](https://ctan.org/pkg/csquotes), respecting `verbatim`/`listings` environments.
- **Flexible Configuration**: options like `language=`, `activate=`, `nested=` and `safeenv=`.

---

## 🛠️ Used Technologies

- **LaTeX2e**
- **csquotes** (quote management and multilingual support)
- **kvoptions** (key=value option parsing)
- **etoolbox** (conditions and extra logic)
- **babel/polyglossia** (optional, for language auto-detection)

---

## 🚀 How to Use

### Prerequisites
- A LaTeX distribution (TeX Live, MikTeX, etc.)
- `csquotes` package installed (comes with full distributions)

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Boudenzin/SmartAspas.git
   

2. In your `.tex` document, add:
   ```latex
   \usepackage[english]{babel} % or brazil, french...
   \usepackage{smartaspas}
   ```

3. Write normally:
   ```latex
   "Automatic quotes 'working' here"
   ```

---

## ⚙️ Package Options

Options are passed in `\usepackage{smartaspas}`:

- `language=auto|brazil|english|french`
  - Default: `auto` (uses `babel`/`polyglossia` if loaded; fallback = English)
- `activate=true|false`
  - Defines whether the `"` character becomes an automatic shortcut. Default: `true`
- `nested=true|false`
  - Defines whether secondary quotes are activated. Default: `true`
- `safeenv={list}`
  - A list of extra environments where automatic quotes are disabled
  - Example: `safeenv={minted,tcolorboxlisting}`

### Example:
```latex
\usepackage[language=auto,activate=true,nested=true,safeenv={minted}]{smartaspas}
```

---

## 📂 Project Structure

```
SmartAspas/
├── smartaspas.sty          # Main package file
├── exemplo/
│   └── main.tex            # Usage example
├── docs/
│   └── logo.png            # Logo for README
├── LICENSE
└── README.md
```

---

## 📝 Usage Examples

### Portuguese Text
```latex
"Aspas automáticas 'funcionando' em português"
```

### English
```latex
\SmartAspasSetup{language=english}
"Nested 'quotes' working fine"
```

### French
```latex
\SmartAspasSetup{language=french}
"Texte avec 'guillemets français'"
```

### Local Control (does not leak state)
```latex
\begin{smartaspasoff}
Here "the quotes" revert to being literal.
\end{smartaspasoff}
```

---

## 🛡️ Troubleshooting

- **Code environments (listings, minted, verbatim):**
  `csquotes` already disables quotes in these environments. If you use other packages, add them to `safeenv`:
  ```latex
  \usepackage[safeenv={minted}]{smartaspas}
  ```

- **Math mode:**
  If you need quotes in mathematical expressions, use `\text{“…”}` with `amsmath`.

- **Conflicts with packages that use `"` (TikZ, JSON inline, etc.):**
  Use `\smartaspasOff` before the snippet and `\smartaspasOn` after, or wrap it in:
  ```latex
  \begin{smartaspasoff}
  "literal" code
  \end{smartaspasoff}
  ```

- **Engines:**
  - pdfLaTeX → use `\usepackage[T1]{fontenc}` and `\usepackage[utf8]{inputenc}`
  - XeLaTeX/LuaLaTeX → Native Unicode support, quotes "work out of the box"

---

## 🔮 Next Goals

1. Native support for more languages (German, Spanish)
2. `safeenv` presets for `listings` and `minted`
3. Publication on CTAN as an official package

---

## 🐞 Issues

Found a problem or have suggestions?  
Open an **issue** on the repository! Your contribution is very welcome.

---

## 📜 License

This project is under the MIT license. See the [LICENSE](LICENSE) file for more details.


