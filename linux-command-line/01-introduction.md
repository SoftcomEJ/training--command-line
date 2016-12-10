# Introdução

Linha de comando, também chamada de terminal, é uma interface de sistema
baseado em texto. Nela, você é capaz de digitar comandos e a resposta é dada
sempre de forma textual.

Normalmente, uma interface de linha de comando é apresentada como um _prompt_.
Ou seja, conforme você for digitando comandos, os resultados irão aparecendo
após o seu envio. Exemplo:

```bash
user@machine:~$ echo 'Hello, Terminal!'
Hello, World!
user@machine:~$ _
```

Onde a linha 1 indica o _prompt_ (`user@machine`) e o diretório de trabalho
atual (`~softcom`). Logo, é exibido o comando enviado (`echo`) e um parâmetro
(`'Hello, World!'`). Na linha 2 se apresenta o resultado desse comando. Na
linha 3 o _prompt_ é exibido novamente, aguardando o envio de um novo comando.

Como o _prompt_ varia de máquina para máquina e de versão para versão de
sistemas operacionais baseados em Linux, costuma-se utilizar somente o _prompt_
como `<caminho>$`. Essa notação será utilizada no decorrer deste curso.


## Abrindo o terminal

O terminal, em sistemas linux, normalmente se encontra em:

  * Aplicações → Ferramentas do Sistema;
  * Aplicações → Acessórios.


## _Bash_

Existem vários interpretadores de linha de comando, também chamados de shell,
para Linux. **Bash** (_Bourne Again Shell_) é indiscutivelmente o mais popular
entre eles. Caso você tenha curiosidade em saber qual _shell_ você está
utilizando, digite:

```bash
~$ echo $SHELL
  /bin/bash
```

## Atividades

1. Descompacte o arquivo `softcom.zip` na sua **pasta de usuário**, caso queira
   saber qual a sua pasta de usuário, execute o comando <kbd>echo $HOME</kbd>
   no terminal e veja o resultado.
2. No terminal, execute o comando <kbd>cd softcom</kbd> no terminal. Essa pasta
   será utilizada para a execução de exemplos e atividades no decorrer do
   curso.
