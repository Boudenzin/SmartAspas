<p align="center">
  <img src="docs/logo.png" alt="SmartAspas Logo" width="200"/>
</p>

<h1 align="center">SmartAspas</h1>

<p align="center">
  <img src="https://img.shields.io/badge/license-MIT-blue?style=for-the-badge" alt="License">
  <img src="https://img.shields.io/github/repo-size/seu-usuario/latex-smartaspas?style=for-the-badge" alt="Tamanho do Repositório">
  <img src="https://img.shields.io/badge/LaTeX-3D6117?style=for-the-badge&logo=latex&logoColor=white" alt="LaTeX">
</p>

O **SmartAspas** é um pacote LaTeX criado para automatizar o uso de aspas tipográficas.  
Em vez de digitar manualmente ``'' para abrir e fechar aspas, basta escrever `"assim"` que o pacote gera corretamente “aspas curvas” e permite também aninhamento (‘aspas simples’ dentro de “aspas duplas”).  

---

## ✨ Funcionalidades

- **Aspas Automáticas**: converte `"` em aspas tipográficas conforme o idioma.  
- **Suporte a Idiomas**: português (padrão), inglês e francês.  
- **Aninhamento Correto**: suporta aspas simples dentro de aspas duplas.  
- **Compatibilidade**: funciona integrado ao [`csquotes`](https://ctan.org/pkg/csquotes), respeitando `babel` ou `polyglossia`.  
- **Ativar/Desativar**: comandos `\smartaspasOn` e `\smartaspasOff` para alternar o recurso.  
- **Comandos Extras**:  
  - `\aspas{texto}` → gera aspas tipográficas manuais.  
  - `\aspasSimples{texto}` → gera aspas simples explícitas.  

---

## 🛠️ Tecnologias Utilizadas

- **LaTeX2e**  
- **csquotes** (dependência principal)  
- **babel/polyglossia** (para gerenciamento de idiomas)  

---

## 🚀 Como Usar

### Pré-requisitos
- Distribuição LaTeX (TeX Live, MikTeX, etc.)
- Pacote `csquotes` disponível (já vem em distribuições completas).

### Passos

1. Clone o repositório:
   ```bash
   git clone https://github.com/Boudenzin/SmartAspas.git


2. No documento `.tex`, adicione:

   ```latex
   \usepackage[brazil]{babel} % ou english / french
   \usepackage{smartaspas}
   ```

3. Escreva normalmente:

   ```latex
   "Aspas automáticas 'funcionando' aqui"
   ```

4. Compile com `pdflatex`, `xelatex` ou `lualatex`.

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

## 🔮 Próximos Objetivos

1. Adicionar suporte a outros idiomas europeus.
2. Testes mais extensivos com ambientes de código (listings, verbatim).
3. Criar release no CTAN para distribuição oficial.

---

## 🐞 Issues

Encontrou algum problema ou tem sugestões?
Abra uma **issue** no repositório do projeto! Sua contribuição é muito bem-vinda.

---

## 📜 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

```

---

👉 Quer que eu também monte um `exemplo/main.tex` já pronto (com texto de teste em português, inglês e francês) para acompanhar esse README no repo?
```
