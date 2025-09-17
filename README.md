<h1 align="center">SmartAspas</h1>

<p align="center">
  <img src="https://img.shields.io/badge/license-MIT-blue?style=for-the-badge" alt="License">
  <img src="https://img.shields.io/github/repo-size/Boudenzin/SmartAspas?style=for-the-badge" alt="Tamanho do Repositório">
  <img src="https://img.shields.io/badge/LaTeX-3D6117?style=for-the-badge&logo=latex&logoColor=white" alt="LaTeX">
</p>

O **SmartAspas** é um pacote LaTeX criado para automatizar o uso de aspas tipográficas.  
Com ele, você pode escrever `"assim 'aninhado' aqui"` e o pacote converte para **“aspas curvas”** e **‘aspas simples’** corretas, de acordo com o idioma.  

---

## ✨ Funcionalidades

- **Aspas Automáticas**: converte `"` em aspas tipográficas.  
- **Suporte Multilíngue**: português, inglês, francês (ou autodetecção via `babel`/`polyglossia`).  
- **Aninhamento Correto**: suporte a aspas secundárias dentro das primárias.  
- **Controle Local**: ambientes `smartaspasoff` e `smartaspason` para ligar/desligar dentro de blocos.  
- **Compatibilidade**: integração com [`csquotes`](https://ctan.org/pkg/csquotes), respeitando ambientes verbatim/listings.  
- **Configuração Flexível**: opções como `language=`, `outerquote=`, `nested=` e `safeenv=`.  

---

## 🛠️ Tecnologias Utilizadas

- **LaTeX2e**  
- **csquotes** (dependência principal)  
- **kvoptions** (gerenciamento de opções)  
- **etoolbox** (lógica condicional)  
- **babel/polyglossia** (opcional, para autodetecção de idioma)  

---

## 🚀 Como Usar

### Pré-requisitos
- Uma distribuição LaTeX (TeX Live, MikTeX etc.)
- Pacote `csquotes` instalado (já incluso nas distribuições completas)

### Instalação

1. Clone o repositório:
   ```bash
   git clone https://github.com/Boudenzin/SmartAspas.git

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
* `outerquote=true|false`

  * Define se `"` vira atalho automático. Padrão: `true`.
* `nested=true|false`

  * Define se aspas secundárias são ativadas. Padrão: `true`.
* `safeenv={lista}`

  * Lista de ambientes extras onde as aspas automáticas são desativadas.
  * Exemplo: `safeenv={minted,tcolorboxlisting}`

### Exemplo:

```latex
\usepackage[language=auto,outerquote=true,nested=true,safeenv={minted}]{smartaspas}
```

---

## 📂 Estrutura do Projeto

```
latex-smartaspas/
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

### Texto normal

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

### Controle local

```latex
\begin{smartaspasoff}
Aqui "as aspas" voltam a ser literais.
\end{smartaspasoff}
```

---

## 🔮 Próximos Objetivos

1. Suporte nativo a mais idiomas europeus.
2. Testes adicionais com pacotes como `minted` e `tcolorbox`.
3. Publicar no CTAN como pacote oficial.

---

## 🐞 Issues

Encontrou algum problema ou tem sugestões?
Abra uma **issue** no repositório! Sua contribuição é muito bem-vinda.

---

## 📜 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.



