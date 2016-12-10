# Permissão e proprietários

O Linux, assim como os demais sistemas operacionais, possuem permissões e
proprietários em arquivos e pastas. Cada arquivo no linux tem três tipos de
permissão:

  * `read`: é permitido ver o conteúdo do arquivo;
  * `write`: é permitido alterar o conteúdo do arquivo;
  * `execute`: é permitido executar caso o arquivo seja um script.

Para cada arquivo existem 3 categorias proprietárias para quem podemos
especificar essas permissões, sendo eles:

  * `owner`: a única pessoas que é dona do arquivo (normalmente quem criou o
    arquivo);
  * `group`: todos os usuários pertencentes ao mesmo grupo;
  * `others`: qualquer pessoa (público).


## Visualizar permissões de diretórios e arquivos

Você pode ver as permissões de um determinado arquivo com o seguinte comando
<kbd>ls -l [caminho]</kbd>. Como vimos anteriormente, esse comando permite
que sejam exibidos informações adicionais na listagem do diretório, sendo que
as informações de permissões são exibidas na primeira coluna, que indicam:

  * O primeiro caractere representa se é um arquivo (`-`) ou um diretório
    (`d`);
  * Os próximos 9 caracteres indicam respectivamente as permissões de cada
    categoria proprietária: `owner`, `group` e `others`.
    - Quando a categoria contém um `r`, então ela pode ler o arquivo;
    - Quando a categoria contém um `w`, então ela pode escrever no arquivo;
    - Quando a categoria contém um `x`, então ela pode executar o arquivo.

Ou seja, um resultado `-rwxrw-r--` indica:

  * O arquivo não é um diretório;
  * O `owner` do arquivo pode ler, escrever e executar o arquivo;
  * O `group` do arquivo pode ler e escrever, mas não pode executar o arquivo;
  * Qualquer outro usuário pode ler o arquivo, mas não pode escrever nesse
    arquivo nem executá-lo.


## Mudanças de permissão

Você pode alterar as permissões de um determinado arquivo ou diretório
utilizando o comando <kbd>chmod</kbd> (_Change Mode_), para isso basta digitar:

```bash
~/softcom$ chmod [permissões] [caminho]
```

Onde `[permissões]` deve ser substituído por:

  * A categoria proprietária: `u` para `owner`, `g` para `group` e `o` para
    `others`, caso ela não seja aplicada as restrições para todas as
    categorias;
  * Garantir (`+`) ou negar (`-`) a permissão;
  * A operação, com `r` para leitura, `w` para escrita e `x` para a execução.

Dessa forma, o comando <kbd>chmod ug+rwx [diretório]</kbd> significa que
foram adiciona para a categoria de `owner` e `group` as permissões e leitura,
escrita e execução ao `[diretório]`, e deixa inalterada as permissões para a
categoria `others`.
