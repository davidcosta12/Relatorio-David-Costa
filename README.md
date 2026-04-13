# PESTI — Template de Relatório de Estágio (ISEP)

Template LaTeX para o relatório de estágio da unidade curricular **PESTI** do Instituto Superior de Engenharia do Porto (ISEP).

---

## Pré-requisitos

Antes de compilar, certifica-te de que tens instalado:

- Uma distribuição LaTeX completa:
  - **macOS** → [MacTeX](https://www.tug.org/mactex/)
  - **Linux** → `sudo apt install texlive-full` (Debian/Ubuntu)
  - **Windows** → [MiKTeX](https://miktex.org/) ou [TeX Live](https://www.tug.org/texlive/)
- **latexmk** (incluído nas distribuições acima)
- **Biber** (incluído nas distribuições acima; usado para a bibliografia)
- **makeglossaries** (incluído no pacote `glossaries` do TeX Live/MacTeX)

---

## Compilar e gerar o PDF

### Opção 1 — com `make` (recomendado)

```bash
make
```

O PDF gerado fica em `main.pdf` na raiz do projeto.

Para limpar os ficheiros auxiliares gerados durante a compilação:

```bash
make clean
```

Para uma limpeza mais profunda (incluindo cache do Biber e pasta `build/`):

```bash
make clean-all
```

### Opção 2 — com `latexmk` diretamente

```bash
latexmk -r latexmk.rc -outdir=build -auxdir=build -pdf \
  -pdflatex="pdflatex -interaction=nonstopmode" -use-make main.tex
mv build/main.pdf .
```

---

## Ver o PDF

Após a compilação, o ficheiro `main.pdf` é gerado na raiz do repositório. Podes abri-lo com qualquer leitor de PDF:

- **macOS** → Pré-visualização (abre automaticamente com duplo clique)
- **Linux** → `xdg-open main.pdf` ou `evince main.pdf`
- **Windows** → duplo clique no ficheiro

Se usas **VS Code**, instala a extensão [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) para compilar e pré-visualizar o PDF diretamente no editor.

---

## Estrutura do projeto

```
.
├── main.tex                  # Ficheiro principal
├── PESTI-style.cls           # Classe LaTeX do template ISEP
├── mainbibliography.bib      # Referências bibliográficas
├── latexmk.rc                # Configuração do latexmk (glossários)
├── Makefile                  # Automatização da compilação
├── frontmatter/
│   ├── frontmatter.tex       # Capa, resumo, agradecimentos, etc.
│   └── assets/               # Logos ISEP/DEI
├── chapters/
│   ├── ch1/chapter1.tex      # Capítulo 1
│   ├── ch2/chapter2.tex      # Capítulo 2
│   └── ...
└── appendices/
    └── appendixA.tex         # Apêndice A
```

---

## Licença

Template originalmente baseado em [MastersDoctoralThesis](http://www.LaTeXTemplates.com), licenciado sob [CC BY-NC-SA 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/). Adaptado para o estilo PESTI/ISEP.
