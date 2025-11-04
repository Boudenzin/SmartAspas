<h1 align="center">SmartAspas</h1>

<p align="center">
  <img src="https://img.shields.io/badge/license-MIT-blue?style=for-the-badge" alt="License">
  <img src="https://img.shields.io/github/repo-size/Boudenzin/SmartAspas?style=for-the-badge" alt="Tamanho do Repositório">
  <img src="https://img.shields.io/badge/LaTeX-3D6117?style=for-the-badge&logo=latex&logoColor=white" alt="LaTeX">
</p>

O **SmartAspas** é um pacote LaTeX que automatiza o uso de aspas tipográficas.  
Em vez de escrever manualmente ``'' ou `\enquote{}`, basta digitar `"assim 'aninhado' aqui"` e o pacote converte automaticamente para **“aspas curvas”** e **‘aspas simples’**, respeitando o idioma do documento.

---

## ✨ Funcionalidades

- **Aspas Automáticas**: converte `"` em aspas tipográficas.  
- **Suporte Multilíngue**: português, inglês e francês (ou autodetecção via `babel`/`polyglossia`).  
- **Aninhamento Correto**: aspas secundárias dentro das primárias.  
- **Controle Local**: ambientes `smartaspasoff` e `smartaspason` desligam/ligam dentro de blocos sem vazar estado.  
- **Compatibilidade**: integra-se ao [`csquotes`](https://ctan.org/pkg/csquotes), respeitando ambientes `verbatim`/`listings`.  
- **Configuração Flexível**: opções como `language=`, `activate=`, `nested=` e `safeenv=`.  

---

## 🛠️ Tecnologias Utilizadas

- **LaTeX2e**  
- **csquotes** (gestão de aspas e multilíngue)  
- **kvoptions** (parsing de opções key=value)  
- **etoolbox** (condições e lógica extra)  
- **babel/polyglossia** (opcional, para autodetecção de idioma)  

---

## 🚀 Como Usar

### Pré-requisitos
- Uma distribuição LaTeX (TeX Live, MikTeX etc.)
- Pacote `csquotes` instalado (vem em distribuições completas)

### Instalação

1. Clone o repositório:
   ```bash
   https://github.com/Boudenzin/SmartAspas.git

2. No documento `.tex`, adicione:

   ```latex
   \usepackage[brazil]{babel} % ou english, french...
   \usepackage{smartaspas}
   ```

3. Escreva normalmente:

   ```latex
   "Aspas automáticas 'funcionando' aqui"
   ```

---

## ⚙️ Opções do Pacote

As opções são passadas no `\usepackage{smartaspas}`:

* `language=auto|brazil|english|french`

  * Padrão: `auto` (usa `babel`/`polyglossia` se carregado; fallback = inglês).
* `activate=true|false`

  * Define se o caractere `"` vira atalho automático. Padrão: `true`.
* `nested=true|false`

  * Define se aspas secundárias são ativadas. Padrão: `true`.
* `safeenv={lista}`

  * Lista de ambientes extras onde as aspas automáticas são desativadas.
  * Exemplo: `safeenv={minted,tcolorboxlisting}`

### Exemplo:

```latex
\usepackage[language=auto,activate=true,nested=true,safeenv={minted}]{smartaspas}
```

---

## 📂 Estrutura do Projeto

```
SmartAspas/
├── smartaspas.sty         # Arquivo principal do pacote
├── exemplo/
│   └── main.tex           # Exemplo de uso do pacote
├── docs/
│   └── logo.png           # Logo para README
├── LICENSE
└── README.md
```

---

## 📝 Exemplos de Uso

### Texto em português

```latex
"Aspas automáticas 'funcionando' em português"
```

### Inglês

```latex
\SmartAspasSetup{language=english}
"Nested 'quotes' working fine"
```

### Francês

```latex
\SmartAspasSetup{language=french}
"Texte avec 'guillemets français'"
```

### Controle local (não vaza estado)

```latex
\begin{smartaspasoff}
Aqui "as aspas" voltam a ser literais.
\end{smartaspasoff}
```

---

## 🛡️ Solução de Problemas

* **Ambientes de código (listings, minted, verbatim):**
  O `csquotes` já desativa aspas nesses ambientes. Se usar outros pacotes, adicione-os em `safeenv`:

  ```latex
  \usepackage[safeenv={minted}]{smartaspas}
  ```

* **Math mode:**
  Se precisar de aspas em expressões matemáticas, use `\text{“…”}` com `amsmath`.

* **Conflitos com pacotes que usam `"` (TikZ, JSON inline, etc.):**
  Use `\smartaspasOff` antes do trecho e `\smartaspasOn` depois, ou envolva em:

  ```latex
  \begin{smartaspasoff}
  código "literal"
  \end{smartaspasoff}
  ```

* **Motores:**

  * pdfLaTeX → use `\usepackage[T1]{fontenc}` e `\usepackage[utf8]{inputenc}`.
  * XeLaTeX/LuaLaTeX → Unicode nativo, aspas “funcionam direto”.

---

## 🔮 Próximos Objetivos

1. Suporte nativo a mais idiomas (alemão, espanhol).
2. Presets de `safeenv` para `listings` e `minted`.
3. Publicação no CTAN como pacote oficial.

---

## 🐞 Issues

Encontrou algum problema ou tem sugestões?
Abra uma **issue** no repositório! Sua contribuição é muito bem-vinda.

---

## 📜 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.
