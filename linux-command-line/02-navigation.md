# Navegação no sistema de arquivos

## Diretório de trabalho

Em interfaces de linha de comando, um conceito importante é o **Diretório de
Trabalho** (_Working Directory_), que é nada mais do que o atual diretório onde
os comandos do terminal são executados. Muitos comandos usam a informação do
diretório de trabalho para serem executados.

Para saber em qual diretório você se encontra, use o comando <kbd>pwd</kbd>
(_Print Working Directory_).

```bash
~/softcom$ pwd
  /home/<user>/softcom
```

Onde `<user>` é o nome do seu usuário.


## Listagem de diretórios

Para saber qual o conteúdo do diretório atual, utiliza-se o comando
<kbd>ls</kbd>.

```bash
~/softcom$ pwd
  Code Projects  Documents  Images  john-galt.md
```

Não é necessário você ter que estar em um diretório para listar ele, por
exemplo, vamos listar a pasta /etc do sistema:

```bash
~/softcom$ ls /etc
  ...
```

Alguns parâmetros podem ser utilizados para comando, como o <kbd>-l</kbd> que
faz uma listagem mais detalhada:

```bash
~/softcom$ ls -l
  total 16
  drwxrwxr-x 2 user user 4096 Dec  5 22:54 Documents
  drwxrwxr-x 2 user user 4096 Dec  5 22:30 Images
  -rw-rw-r-- 1 user user  310 Dec  5 23:00 john-galt.md
  drwxrwxr-x 3 user user 4096 Dec  5 22:39 Projects
```

Onde a resposta indica:

  * Na primeira linha da resposta, o número total de arquivos ou diretórios do
    diretório de trabalho.
  * Nas próximas linhas indicam detalhes de cada arquivo/diretório, que exibem,
    em sequência:
      - Se o arquivo é um arquivo normal (`-`) ou um diretório (`d`);
      - As permissões do arquivo;
      - A quantidade de blocos;
      - O nome de do usuário o qual pertence o arquivo;
      - O nome do grupo o qual pertence o arquivo;
      - O tamanho do arquivo;
      - Última data de modificação;
      - O nome do arquivo;


## Caminhos Absolutos e Caminhos Relativos

Para indicar caminhos para um comando, tal como o <kbd>ls</kbd>, podemos
utilizar tanto **Caminhos relativos** quanto **Caminhos absolutos**. Os
arquivos em sistemas Linux são organizados de forma hierárquica, como uma
árvore de várias folhas, onde a raiz dessa árvore é indicada pelo diretório
**_root_** (`/`).

Caminhos absolutos são caminhos que indicam todo o caminho a partir do
diretório _root_ do sistema. Por isso, caminhos absolutos sempre começam com
`/`. Já caminhos relativos são sempre referenciados pelo diretório de trabalho
do terminal. Dessa forma, caminhos relativos nunca começam com `/`, mas sim com
uma referência direta do diretório o qual se pretende alcançar. Veja o exemplo:

```bash
~/softcom$ pwd
  /home/[usuário]/softcom
~/softcom$ ls /home/user/softcom/Documents/
  cicero-1.txt  cicero-2.txt  far-far-away.txt  kafka.md  ...
~/softcom$ ls Documents
  cicero-1.txt  cicero-2.txt  far-far-away.txt  kafka.md  ...
```

Note que estamos acessando o mesmo diretório, porém na linha 3 utilizados o
caminho absoluto enquanto na linha 5 utilizamos o caminho relativo ao diretório
de trabalho exibido na linha 1.


## Referências especiais

Existem algumas referências de caminhos criadas para facilitar a utilização de
linha de comando. O diretório atual (`.`), listado com o comando
<kbd>pwd</kbd>. Veja:

```bash
~/softcom$ ls Images
  Amplituhedron.jpg  Color.jpg  Planets.jpg  Softcom.png
~/softcom$ ls ./Images
  Amplituhedron.jpg  Color.jpg  Planets.jpg  Softcom.png
```

Diretório do usuário (`~`), ou seja, a pasta do seu usuário, normalmente
localizada em `/home/[usuário]` (Onde `[usuário]` é nome do seu usuário).

```bash
~/softcom$ ls /home/[usuário]
  ...
~/softcom$ ls ~
  ...
```

Diretório pai (`..`), ou seja, o diretório de nível hierárquico superior.

```bash
~/softcom$ ls Documents/../Images
  Amplituhedron.jpg  Color.jpg  Planets.jpg  Softcom.png
```


## Mudando o diretório de trabalho

Para mudar o diretório de trabalho, utiliza-se o comando
<kbd>cd [destino]</kbd> (_Change Directory_). Veja:

```bash
~/softcom$ cd Documents
softcom/Documents$ ls
  cicero-1.txt  cicero-2.txt  far-far-away.txt  kafka.md  ...
```

Observe que o caminho do prompt se altera. Veja outros exemplos:

```bash
softcom/Documents$ cd ..
~/softcom$ ls
  Code Projects  Documents  Images  john-galt.md
```

```bash
softcom/Documents$ cd /
/$ ls
  bin   etc   lib   mnt   proc    srv   tmp   var   ...
```

Perceba que o prompt agora indica o diretório o qual você se encontra — e com
isso, todos os caminhos relativos que você utilizar terão como referência ele.
Caso você use o comando <kbd>cd</kbd> sem qualquer caminho, ele sempre irá te
levar para sua pasta de usuário (`/home/[usuário]`).

```bash
/$ cd
~$ pwd
  /home/user
```

## Autocompletar e ajuda

Toda vez que você quiser acessar um diretório de um caminho, utilize o
<kbd>Tab</kbd> para autocompletar ou listar opções disponíveis.

Caso você um dia precise de ajuda com qualquer comando que seja, utilize o
comando <kbd>help [comando]</kbd> ou <kbd>man [comando]</kbd> (_Manual_) para
visualizar um manual sobre o comando.


## Atividades

  1. Execute os comandos para:
    * Exibir uma lista dos arquivos do diretório `/etc`:
    * Exibir uma lista detalhada dos arquivos do diretório `/var/log`
    * Navegue para o diretório `/bin` e execute uma listagem simples com
      caminho relativo.
  2. Navegue para a pasta de usuário com 3 métodos diferentes: (Caminho
     relativo, Caminho Absoluto e `~`).
