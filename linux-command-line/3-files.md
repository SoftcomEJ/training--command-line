# Sobre arquivos

## Todas as coisas são arquivos

Em Linux, todas as coisas são arquivos. Um arquivo de texto é um arquivo, um
diretório é um arquivo, o teclado é um arquivo, o monitor é um arquivo e assim
por diante. Ter isso em mente auxilia o entendimento de como se manipula
recursos em Linux.

Outro ponto importante é que em Linux a extensão de um arquivo não determina
que tipo o arquivo tem. Para determinar se um arquivo é uma imagem, texto ou
música, o sistema operacional olha o conteúdo do arquivo. Para saber mais
informações de um arquivo, utilizamos o comando <kbd>file</kbd>.

```bash
~/softcom$ file john-galt.md
  john-galt.md: UTF-8 Unicode text
```

É importante lembrar que nomes de arquivos são sempre case sensitives, ou seja,
`FILE.txt` é diferente de `file.txt`, que também é diferente de `file.tXt`.
Arquivos e diretórios com espaços também podem ser criados, mas precisam de um
tratamento especial em seu nome com a utilização de quotes (`‘’`) ou de escape
bom barra (`\ `).

```bash
~/softcom$ ls
  Code Projects  Documents  Images  john-galt.md
~/softcom$ ls 'Code Projects'
  hello-world
~/softcom$ ls Code\ Projects
  hello-world
```


## Arquivos ocultos

Um arquivo é considerado “oculto” em Linux se seu nome se inicia com um ponto
(`.`). Por padrão, o comando <kbd>ls</kbd> não exibe arquivos ocultos a não ser
se for explicitamente requisitado. Para exibir arquivos ocultos, utiliza-se o
parâmetro `-a`. Veja:

```bash
~/softcom$ ls
  Code Projects  Documents  Images  john-galt.md
~/softcom$ ls -a
  .  ..  Code Projects  Documents  .hidden  Images  john-galt.md
```

Observe que tanto o caminho atual (`.`) quanto o caminho pai (`..`) são também
arquivos do diretório, mas como começam com `.`, são arquivos ocultos.

## Atividades

1. Execute o comando file para diversos arquivos no seu computador e veja os
   resultados.
2. Liste todos os arquivos (incluindo os ocultos) para o diretório `~`.
