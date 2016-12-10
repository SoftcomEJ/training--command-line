# Manipulação de Arquivos

## Criando um diretório

Para criar um diretório no diretório atual utiliza-se o comando
<kbd>mkdir [destino]</kbd> (_Make Directory_). Veja no exemplo:


```bash
~/softcom$ ls
  Code Projects  Documents  Images  john-galt.md
~/softcom$ mkdir Music
  Code Projects  Documents  Images  john-galt.md  Music
```

Você pode criar um diretório com um caminho relativo ou absoluto. Porém ele só
cria um diretório por vez. Caso você queira todos os diretórios relacionados ao
caminho, utiliza-se o parâmetro <kbd>-p</kbd>. Veja:

```bash
~/softcom$ mkdir -p Music/Gorillaz/2001-Gorillaz
~/softcom$ ls -a Music/Gorillaz
  .  ..  2001-Gorillaz
```

## Removendo diretórios

Para remover um diretório, utiliza-se o comando <kbd>rmdir [destino]</kbd>. No
entanto, esse comando não move o arquivo para a “lixeira”, mas efetivamente
apaga o arquivo do diretório, não sendo possível desfazer a operação. Veja o
exemplo:

```bash
~/softcom$ rmdir Music/Gorillaz/2001-Gorillaz/
~/softcom$ ls -a Music/Gorillaz
  .  ..
```

Outra importante observação é que um diretório só pode ser removido com o
comando <kbd>rmdir</kbd> se estiver vazio.


## Criando um arquivo vazio

Um arquivo vazio pode ser criado com o comando <kbd>touch [destino]</kbd>.
Veja:

```bash
~/softcom$ touch file1
~/softcom$ ls -la
  total 32
  drwxrwxr-x  7 user user 4096 Dec  6 00:08 .
  drwxr-xr-x 56 user user 4096 Dec  5 22:29 ..
  drwxrwxr-x  3 user user 4096 Dec  5 22:39 Code Projects
  drwxrwxr-x  2 user user 4096 Dec  5 22:54 Documents
  -rw-rw-r--  1 user user    0 Dec  6 00:08 file1
  drwxrwxr-x  2 user user 4096 Dec  5 23:33 .hidden
  drwxrwxr-x  2 user user 4096 Dec  5 22:30 Images
  -rw-rw-r--  1 user user  310 Dec  5 23:00 john-galt.md
  drwxrwxr-x  3 user user 4096 Dec  5 23:57 Music
```

O comando <kbd>touch</kbd> também serve para atualizar a data de última
modificação de um arquivo (como visualizado na saída do comando
<kbd>ls -la</kbd>). Porque de forma geral ele não altera nada no arquivo, só
muda a data de última manipulação.


## Copiando arquivos

Um arquivo ou diretório pode ser copiado com o comando
<kbd>cp [origem] [destino]</kbd> (_Copy_). Lembre-se que o comando
<kbd>cp</kbd> aceita qualquer caminho. Se você quiser copiar um arquivo de/para
outro diretório, basta especificar o caminho da origem ou destino. Caso você
direcione o destino para um diretório, o arquivo será copiado para dentro desse
diretório com o mesmo nome da origem. Veja um exemplo.

```bash
~/softcom$ ls
  Code Projects  Documents  file1  Images  john-galt.md  Music
~/softcom$ cp file1 copy1
~/softcom$ ls
  Code Projects  copy  Documents  file1  Images  john-galt.md  Music
```

Para copiar diretórios (e todo o seu conteúdo interno), é necessário utilizar o
parâmetro <kbd>-r</kbd> (_Recursive_). Dessa forma, todos os arquivos
hierarquicamente abaixo desse diretório, serão copiados. Veja:

```bash
~/softcom$ cp -r Music MusicCopy
  Code Projects  Documents  file1  Images  john-galt.md  Music
~/softcom$ ls
  Code Projects  copy  Documents  file1  Images  john-galt.md  Music MusicCopy
~/softcom$ ls MusicCopy
  Gorillaz
```


## Movendo arquivos

Você pode mover, também chamado de recortar, arquivos com o comando
<kbd>mv [origem] [destino]</kbd> (_Move_). O comando <kbd>mv</kbd> opera de
forma similar ao comando <kbd>cp</kbd>, com a diferença de que não é necessário
utilizar o parâmetro <kbd>-r</kbd> quando for necessário mover diretórios.

Veja um exemplo:

```bash
~/softcom$ ls
  Code Projects  copy  Documents  file1  Images  john-galt.md  Music MusicCopy
~/softcom$ mv copy1 MusicCopy
~/softcom$ mv file1 MusicCopy/file2
  Code Projects  copy  Documents  file1  Images  john-galt.md  Music MusicCopy
~/softcom$ ls MusicCopy
  copy1   file2   Gorillaz
```


## Renomeando arquivos

Você também pode renomear arquivos ou diretórios com o comando <kbd>mv</kbd>,
basta você manter o arquivo no mesmo diretório. Veja:

```bash
~/softcom$ cd Images
~/softcom/Images$ ls
  Amplituhedron.jpg  Color.jpg  Planets.jpg  Softcom.png
~/softcom$ mv Softcom.png Softcom-logo.png
~/softcom/Images$ ls
  Amplituhedron.jpg  Color.jpg  Planets.jpg  Softcom-Logo.png
~/softcom/Images$ cd ..
```


## Removendo arquivos ou diretórios não vazios

Para remover arquivos, utiliza-se o comando <kbd>rm [destino]</kbd> (*Remove*),
assim como o comando <kbd>rmdir</kbd>, o comando <kbd>rm</kbd> não pode ser
“desfeito”, pois exclui permanentemente o arquivo. Para remover diretórios não
vazios, utiliza-se também o parâmetro <kbd>-r</kbd>. Veja:

```bash
~/softcom$ rm MusicCopy/copy1
~/softcom/Images$ ls MusicCopy
  file2   Gorillaz
~/softcom$ rm -r MusicCopy
~/softcom$ ls
  Code Projects  copy  Documents  file1  Images  john-galt.md  Music
```

## Atividades

1. Crie a seguinte estrutura de arquivos:
  ```
  Code\ Projects/softcom.github.io/
  ├─assets/
  │ ├─images/
  │ ├─css/
  │ ├─js/
  │ └─fonts/
  ├─about/
  ├─contact/
  ├─products/
  ├─README.md
  └─LICENSE
  ```
2. Apague o arquivo `LICENSE` e o diretório `assets/fonts`.
