# Redirecionamento de I/O

Como visto anteriormente, tudo em Linux é um arquivo, desde arquivos
propriamente ditos, diretórios, _socket_ de comunicação para rede, entrada de
teclado e saída de texto. Nesta seção iremos apresentar um mecanismo muito
utilizado por programas de linha de terminal chamado **Redirecionamento de
entrada e saída**.


## Saída Padrão

A saída da execução de um comando, tal como um <kbd>ls</kbd>, normalmente é
feita na tela, mas esse não precisa necessariamente ser o caso. Podemos
utilizar o operador <kbd>></kbd> para redirecionarmos a saída do comando
anterior a um arquivo específico. Veja no exemplo:

```bash
~/softcom$ ls Documents
  cicero-1.txt  cicero-2.txt  far-far-away.txt  kafka.md ...
~/softcom$ ls Documents > ls-out.txt
~/softcom$ ls
  Code Projects  Documents  Images  john-galt.md  ls-out.txt  Music
```

Tente visualizar o conteúdo de ls-out.txt com o <kbd>less</kbd>.

Toda vez que o comando <kbd>ls > ls-out.txt</kbd>, o arquivo `ls-out.txt` será
reescrito. Caso você queira que o resultado de um comando seja acrescentado ao
fim do arquivo, utilize o operador <kbd>>></kbd>. Veja:

```bash
~/softcom$ ls images
  Amplituhedron.jpg  Color.jpg  Planets.jpg  Softcom-Logo.png
~/softcom$ ls Images >> ls-out.txt
```

Abra o conteúdo do arquivo `ls-out.txt` com o <kbd>less</kbd> para ver o
resultado.


## Entrada Padrão

Normalmente um programa de linha de comando usa como entrada padrão a entrada
de teclado do computador, porém esse não precisa necessariamente ser o caso.
Você pode redirecionar uma entrada padrão de um programa com o operador
<kbd><</kbd>. Veja um exemplo com o programa <kbd>sort</kbd>:

```bash
~/softcom$ sort < ls-out.txt
  Amplituhedron.jpg
  cicero-1.txt
  cicero-2.txt
  Color.jpg
  far-far-away.txt
  kafka.md
  lorem-ipsum.md
  pangram.md
  Planets.jpg
  Softcom-Logo.png
```

Veja que o <kbd>sort</kbd> executa uma ordenação das linhas de um arquivo. Caso
queiramos salvar o resultado do comando em outro arquivo, basta redirecionarmos
usa saída.

```bash
~/softcom$ sort < ls-out.txt > ls-out-sorted.txt
```

E veja o resultado com o <kbd>less</kbd> no arquivo `ls-out-sorted.txt`


## _Pipelines_

O mais útil de redirecionar entradas e saídas na linha de comando é poder
conectar múltiplos comandos juntos no que chamamos de **_pipeline_**. Com
_pipelines_ a saída padrão de um comando é automaticamente utilizada como
entrada padrão de outro comando, bastando separar os comandos por um
<kbd>|</kbd>. Veja o exemplo:

```bash
~/softcom$ ls -l /etc | less
```

Veja que esse comando permite que qualquer saída de um comando seja exibida de
forma amigável pelo <kbd>less</kbd>, o que é extremamente útil onde a interface
do terminal é limitada.

Com _pipelines_ você pode fazer coisas muito interessantes como:

  * <kbd>ls -lt | head</kbd> ― Listar os 10 arquivos mais novos do diretório;
  * <kbd>du | sort -nr</kbd> — Listar os diretórios por ordem de espaço de
    ocupação de disco;
  * <kbd>find . -type f -print | wc -l</kbd> — Lista o número de arquivos no
    diretório atual e em todos os subdiretórios.


## Filtros

Um tipo de programa frequentemente utilizado em _pipelines_ são os chamados
**Filtros**. Filtros pegam uma entrada padrão, executam uma operação e devolvem
o resultado na saída padrão. Desse modo, eles podem ser combinados para
realizar tarefas complexas.

A lista de filtros é bastante grande, pois são normalmente programas
independentes, porém os mais utilizados já vem de forma padrão na linha de
comando _Bash_. Entre eles:

  * <kbd>cat</kbd>: Exibe na saída a entrada;
  * <kbd>head</kbd>: Exibe na saída as 10 primeiras linhas da entrada;
  * <kbd>tail</kbd>: Exibe na saída as 10 últimas linhas da entrada;
  * <kbd>wc</kbd>: Exibe na saída a quantidade de caracteres da entrada;
  * <kbd>sort</kbd>: Exibe na saída a entrada ordenada por linha;
  * <kbd>grep</kbd>: Exibe na saída as linhas que “casam” com uma expressão
    regular;
  * <kbd>uniq</kbd>: Exibe na saída somente linhas não duplicadas;

Todos esses programas possuem parâmetros que alteram seu comportamento, e que
podem ser visualizados com a ajuda do comando <kbd>man [filtro]</kbd>, que
exibe um manual do comando.


## Atividades

1. Visualize o arquivo `Code Projects/entries.txt` com o <kbd>less</kbd>;
2. Exiba os 10 primeiras entradas na tela;
3. Ordene as entradas e mostre-os na tela;
4. Ordene as entradas sem duplicatas e salve no arquivo
   `Code Projects/contacts.txt`;
5. Exiba a quantidade de contatos no arquivo `Code Projects/contacts.txt`
   (Dica: use o parâmetro <kbd>-l</kbd> para contar a quantidade de linhas).
