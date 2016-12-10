# Controle de tarefas

Apesar de você soment poder visualizar um processo sendo executado por vez,
é possível no linux executar vários comandos que rodem em sequência ou em
paralelo, que continuam executando no plano de fundo.


## Execução de comandos sequenciais e paralelos

Para executar comandos sequenciais, você precisa inserir um <kbd>;</kbd> entre
os comandos. Veja:

```bash
~/softcom$ ls Documents; ls Images
cicero-1.txt  cicero-2.txt  far-far-away.txt  kafka.md  lorem-ipsum.md pangram.md
Amplituhedron.jpg  Color.jpg  Planets.jpg  softcom.png
```

Para executar comandos em paralelo é necessário inserir um <kbd>&</kbd> ao
final do comando.

```bash
~/softcom$ ls Documents && ls Images
```

Lembre-se que os comandos realizados em paralelo irão competir pela saída
padrão, gerando bloqueios e condições de corrida. Por isso, caso você dependa
da saída o programa para alguma coisa, é preciso tomar cuidado pois resultados
inesperados podem ocorrer.


## Congelando tarefas

Ao executar um programa, você pode pausar a execução utilizando o comando
<kbd>Ctrl</kbd>+<kbd>Z</kbd>. Esse comando congela a execução da tarefa sem
matá-la. Isso pode ser útil, por exemplo, quando precisa verificar alguma outra
informação mas não deseja ter que salvar tudo o que estava fazendo.

Inicie o <kbd>nano -u</kbd> e congele sua execução com
<kbd>Ctrl</kbd>+<kbd>Z</kbd> para testar o comando.

## Listando tarefas

É possível listar as tarefas, congeladas ou não, que estão sendo executadas em
uma sessão do _shell_ com o comando <kbd>jobs</kbd>, veja.

```bash
~/softcom$ jobs -l
  [1]+  23918 Stopped        nano -u
```

Ou seja, a tarefa com o comando <kbd>nano -u</kbd> está parada. Caso você
inicie outras tarefas e as congele-as ou as deixe executando em segundo plano,
ao listar as tarefas com o comando <kbd>jobs</kbd>, todas elas serão listadas.

Tente executar o <kbd>less</kbd> em um arquivo de texto e congelar sua execução
com <kbd>Ctrl</kbd>+<kbd>Z</kbd>. Em seguida, digite no terminal:

```bash
~/softcom$ jobs -l
  [1]-  23918 Stopped        nano -u
  [2]+  24888 Stopped        less Documents/kafka.md
```

Veja que agora temos dois processos congelados. Perceba que o último comando
congelado sempre possui o indicador `+` na listagem.

## Descongelando tarefas

Para isso "descongelar" um processo, utilize o comando <kbd>fg [índice]</kbd>
(_foreground_), onde `[índice]` indica o número da tarefa entre `[ ]` na
listagem do comando <kbd>jobs</kbd>. Caso o índice não seja fornecido, o
comando <kbd>fg</kbd> irá trazer para o primeiro plano a última tarefa
congelada.

Suponha que agora eu queira voltar para a execução do <kbd>nano -u</kbd>,
congelado anteriormente. Nesse caso, digite no terminal:

```bash
~/softcom$ fg 1
```

E a tela principal do terminal volta ao controle do comando congelado
anteriormente.


## Executando tarefas no fundo

Suponha que congelamos uma tarefa, mas queremos que ela continue executando no
plano de fundo, para isso, utilizamos o comando <kbd>bg [índice]</kbd>, onde
`[índice]` é o número da tarefa na listagem do comando <kbd>jobs</kbd>.

Caso queiramos voltar para a tela de um comando executando em plano de fundo,
você pode chamar o comando <kbd>fg</kbd> para ele.


## Identificando tarefas

Toda tarefa possui um identificador, popularmente chamado de **_pid_**
(_Proccess Identification_). O _pid_ de um processo é exibido na segunda coluna
do comando <kbd>jobs -l</kbd>. Vocẽ também pode requisitar o _pid_ de um
comando, caso lembre do nome dele, com o comando <kbd>pidof [comando]</kbd>.
Veja:

```bash
~/softcom$ jobs -l
  [1]-  23918 Stopped        nano -u
  [2]+  24888 Stopped        less Documents/kafka.md
~/softcom$ pidof less
  24888
```

## Matando tarefas

Você pode matar tarefas executando com o comando <kbd>kill [pid]</kbd>, onde
`[pid]` é o identificador do processo.


## Gerência de processos avançanda

Existem outras ferramentas de controle de processo e tarefas avançadas para
utilização no terminal, entre elas se destaca o <kbd>htop</kbd>. Apesar de
normalmente não vir acompanhado da distrubuição linux, com o <kbd>htop</kbd>
é possível realizar várias tarefas, entre elas:

  * Filtrar processos por nome ou comando de execução com <kbd>F4</kbd>;
  * Matar um processo com <kbd>F6</kbd>;
  * Exibir a árvore de processos com <kbd>F5</kbd>.
