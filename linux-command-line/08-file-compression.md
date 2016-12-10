# Compactação e descompactação de arquivos

A compactação de pastas ou arquivos servem para diminuir o espaço final
ocupado, para realizar compactação e descompactação de arquivos temos dois
grupos de comandos básicos, sendo um deles para gerar arquivos **zip** e outro
para arquivos **tar**.


## Compactando e descompactando arquivos zip

Nem todo sistema linux vem instalado os programas <kbd>zip</kbd> e
<kbd>unzip</kbd> realizar essa ação, caso o seu não possua por padrão pode
instalar utilizando o comando:

```bash
~/softcom$ sudo apt-get install zip unzip
```

Depois de instalado, basta digitar o seguinte comando para compactar:

```bash
~/softcom$ zip [destino.zip] [origem]
```

Para descompactar, basta utilizar o comando:

```bash
~/softcom$ unzip [origem.zip] -d [destino]
```

Com isso será descompactado na pasta com o nome informado, se não passar nenhum
parâmetro além do nome do arquivo, a descompactação ocorrerá no diretório
atual.


## Compactando e descompactando arquivos tar

Para compactar use a seguinte sintaxe:

```bash
~/softcom$ tar -zcf [destino.tar] [origem]
```

Para descompactar use a seguinte sintaxe:

```bash
~/softcom$ tar -xvf [origem.tar]
```

Existem várias variações para arquivos tar, tais como tar.gz, tar.br2, entre
outros. O comando <kbd>tar</kbd> é capaz de descompactar todos eles variando os
parâmetros de execução.
