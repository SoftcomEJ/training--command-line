# _Wildcards_

## Introdução

_Wildcards_ é um conjunto de padrões para definir conjunto de arquivos ou
diretórios. Utiliza-se _wildcards_ para criar expressões que facilitem a busca
e a filtragem de resultados na saída do terminal. O conjunto mais básico de
_wildcards_ é composto de:

* `*`- Representa 0 ou mais caracteres;
* `?` - Representa um caracter;
* `[ ]` - Representa uma coleção de caracteres.

## Exemplos

Imagine que temos um diretório com vários arquivos de imagens com diferentes
extensões e queremos somente listar as imagens que possuem a extensão “png”.
Podemos utilizar _wildcards_ para facilitar nossa tarefa:

```bash
~/softcom$ cd Images
~/softcom/Images$ ls *.png
  Softcom-Logo.png
~/softcom/Documents$ cd ..
```

Se imagine em uma situação onde você precise listar todos os arquivos que
possuem um nome com 5 (cinco) caracteres (seja qual for a extensão). Você pode
utilizar também:

```bash
~/softcom$ cd Documents
~/softcom/Documents$ ls ?????.*
  kafka.md
~/softcom/Documents$ cd ..
```

Por exemplo, suponha que você queira listar todos os caracteres que começam com
“f” ou “p”. Você pode utilizar o _wildcard_ `[ ]` para especificar os
caracteres da coleção em seu interior, veja:

```bash
~/softcom$ cd Documents
~/softcom/Documents$ ls [fp]*
  far-far-away.txt  pangram.md
~/softcom/Documents$ cd ..
```

O _wildcard_ `[ ]` também aceita sequências predefinidas. Um exemplo são os
numerais (de 0 a 9), que podem ser ser explicitados na forma de  `[0-9]`. Ou
seja, caso você precise listar todos os arquivos que terminem com um número,
você pode por exemplo:

```bash
~/softcom$ ls -l Documents/cicero-[0-9].txt
  -rw-rw-r-- 1 user user 1171 Dec  5 22:35 Documents/cicero-1.txt
  -rw-rw-r-- 1 user user 1339 Dec  5 22:35 Documents/cicero-2.txt
```


## Atividades

1. Liste todos os arquivos que:
  * Contenham um hífen (“-”);
  * Contenham 6 letras;
  * Contenham 6 letras com extensão “.md”;
  * Contenham dois hífens (“-”).
