# Leitura e edição de arquivos de texto


## Introdução

Em uma interface textual, como a linha de comando, arquivos de texto são
objetos de primeira classe e o terminal oferece ferramentas necessárias para a
leitura e a edição de arquivos de texto seja feita de forma fácil.


## Leitura com o <kbd>less</kbd>

O programa <kbd>less</kbd> tem como objetivo permitir a leitura de um arquivo
na tela do terminal. Veja alguns comandos úteis:

  * <kbd>Page Up</kbd> ou <kbd>B</kbd>: Volta uma página;
  * <kbd>Page Down</kbd> ou <kbd>Space</kbd>: Avança uma página;
  * <kbd>G</kbd>: Avança para o final do arquivo;
  * <kbd>/[caracteres]</kbd>: Busca no arquivo a sequência de caracteres
    informada;
  * <kbd>N</kbd>: Vai para o próximo _match_ da pesquisa anterior;
  * <kbd>H</kbd>: Exibe uma completa lista de comandos disponíveis;
  * <kbd>Q</kbd>: Termina a execução do <kbd>less</kbd>.


## Edição de arquivos com o <kbd>nano</kbd>

O Linux possui diversos editores de texto, com funcionalidades bastante
avançadas e poderosas, que fazem o trabalho do desenvolvedor se tornar muito
mais fácil. No entanto, devido a curva de aprendizagem ser íngreme, muitas
pessoas acreditam que todo editor de texto de linha de comando são complexos e
difíceis de mexer.

Nesta seção iremos aprender sobre o <kbd>nano</kbd>, um editor de texto que
roda na linha de comando e que é bastante simples e fácil de manipular.


### Inicializando o <kbd>nano</kbd>

O <kbd>nano</kbd> pode ser executado de duas formas, a primeira forma abre o
editor em um _buffer_ vazio. Veja:

```bash
~/softcom$ nano -u
```

O parâmetro `-u` serve para adicionar a funcionalidade de “desfazer/refazer” no
programa. Outra forma de abrir o Nano é quando já temos um arquivo já criado e
queremos editá-lo:

```bash
~/softcom$ nano -u Documents/test.txt
```

Caso o arquivo não exista, ele será criado caso você o salve.


### Navegando pelo texto

Para navegar pelo texto, você pode utilizar:

  * As teclas direcionais (<kbd>↑</kbd>, <kbd>→</kbd>, <kbd>↓</kbd> e
    <kbd>←</kbd>) para mover o cursor para o próximo caractere ou linha;
  * As teclas <kbd>Home</kbd> ou <kbd>Ctrl</kbd>+<kbd>A</kbd> para ir ao início
    da linha;
  * <kbd>End</kbd> ou <kbd>Ctrl</kbd>+<kbd>E</kbd> para ir até o fim da linha;
  * <kbd>Page Up</kbd> para ir até a próxima página;
  * <kbd>Page Down</kbd> para ir para a página anterior;

Caso você se perca com o cursor, utilize <kbd>Ctrl</kbd>+<kbd>c</kbd> para
exibir a localização do cursor na tela.


### Requisitando ajuda

Caso surja dúvida com algum comando, você pode acessar o menu de ajuda com
<kbd>Ctrl</kbd>+<kbd>G</kbd> ou <kbd>F1</kbd>.


### Recortar, Copiar e Colar linhas

Para manipular linhas inteiras, você tem a disposição:

  * Recortar linha <kbd>Ctrl</kbd>+<kbd>K</kbd>, remove a linha do texto e a
    coloca no _buffer_;
  * Colar linha <kbd>Ctrl</kbd>+<kbd>U</kbd>, adiciona o conteúdo do _buffer_
    na linha onde o cursor se encontra, passa o conteúdo da linha atual para a
    próxima linha;__

Caso você queira copiar linhas, basta recortá-las e ir colando onde você
precisar, pois o _buffer_ de cópia só é alterado a próxima vez que você
recortar alguma coisa novamente.


### Manipulação de Blocos

Os comandos de recortar <kbd>Ctrl</kbd>+<kbd>K</kbd> e colar
<kbd>Ctrl</kbd>+<kbd>U</kbd> só possuem efeito em linhas inteiras. Caso você
queira copiar blocos de texto, primeiramente você precisa selecioná-los. A
seleção de blocos de texto pode ser feito com o comando
<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>6</kbd>. Esse comando irá adicionar uma
marca a partir da posição atual do cursor. Mover o cursor nesse estado irá
selecionar o texto.

Quando a seleção estiver de acordo com o desejado, você pode tanto aplicar um
recorte <kbd>Ctrl</kbd>+<kbd>K</kbd> para transferi-lo para o buffer. Caso você queira desselecionar o bloco, basta teclar
<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>6</kbd> novamente.


### Desfazer e Refazer alterações

Você pode desfazer as últimas alterações utilizando o atalho
<kbd>Alt</kbd>+<kbd>U</kbd>. Para refazer as últimas operações você pode
utilizar o atalho <kbd>Alt</kbd>+<kbd>E</kbd>. Lembre-se que esse comando só
funcionará se o parâmetro `-u` for utilizado na inicialização do
<kbd>nano</kbd>.


### Localizar e substituir

Você pode utilizar o atalho <kbd>Ctrl</kbd>+<kbd>W</kbd> ou <kbd>F6</kbd> para
realizar pesquisas de sequências de caracteres no texto.

Para Localizar e Substituir você pode utilizar o atalho
<kbd>Ctrl</kbd>+<kbd>\\</kbd>. Quando o Nano encontrar uma ocorrência da sua
pesquisa, ele irá requisar se você deseja substituir ou não, bastando responder
com <kbd>Y</kbd> se sim ou <kbd>N</kbd> caso contrário. Também é possível
utilizar <kbd>A</kbd> para substituir todas as ocorrências.


### Salvando o arquivo

Para salvar o arquivo você pode utilizar o atalho <kbd>Ctrl</kbd>+<kbd>O</kbd>,
ele irá requisitar um nome para o arquivo que pode ser alterado. Caso você não
altere o nome, ele salva em cima do arquivo original.


### Sair

Para sair do Nano utilize o atalho <kbd>Ctrl</kbd>+<kbd>X</kbd>, caso alguma
modificação tenha sido feita no arquivo, ele irá requisitar se você deseja
salvar ou não essas modificações, passado pelo mesmo processo do parágrafo
anterior.
