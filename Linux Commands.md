# Navegação entre diretórios

### Listar diretorios

    ls

Verbosas

    -l - Lista formatada

    -la - Mostra arquivos com arquivos ocultos

### Acessar diretórios

    cd nomeDoDiretorio

Muda para diretório raiz

    cd ~

Muda para diretorio especifico dent odo diretório raiz

    cd ~/

### Mostra diretório atual

    pwd

### Cria diretório de arquivos

    mkdir nomeDoDiretorio

### Deleta Arquivo

    rm arquivo

Verbosas:

    -f - Remove a força
    -r - Remove o diretório

Deleta tudo dentro do diretorio selecionado

    rm -rf /

### Copia arquivos

    cp arquivo1 arquivo2

### renomeia arquivos

    mv arquivo1 arquivo2

### Mover e renomear

    mv arquivo1 diretorio/arquivo2

### Criar arquivos

    touch nomeArquivo

### Ler conteudo do arquivo

    cat arquivo

Permite escrever no arquivo com cat e adcionar texto

    cat > arquivo
    cat >> arquivo

É utilizado para imprimir os últimos números N ou tails de uma entrada

    tail -f arquivo

## Comandos de rede

### Pingar

    ping host

### Descobrir nome do dominio

    whois dominio

### Descobrir DNS do dominio

    dig dominio
    dig -x host

### Baixar arquivos

    wget urlArquivo

Verbosas:

    -c - Continua download
    -r - Recupera download da url

### Mostra url completa do site

    curl url

    curl -o meh.html url

### Conectar com host como usuário

    ssh user@host

Verbosas

    ssh -p porta user@host - Conecta usando porta
    ssh -D porta user@host - Conecta usando porta vinculada

## Processos

Mostra processos ativos

    ps

Mostrar com detalhes

    ps aux

### Encerrar processos

Encerra processo através do ID dele, no caso o PID indicado na pesquisa ps aux

    kill pid

Encessar todos os processos com o mesmo nome

    killall nome

## Informações do sistema

### Mostra data atual

    date

### Mostra uptime

    uptime

### Mostra em qual usuário está logado

    whoami

### Mostra quem está online

    w

### Mostra infos da cpu / memoria

    cat /proc/cpuinfo
    cat /proc/meminfo

### Mostra quantidade de memória livre

    free

### Mostra a quantidade de memória que o diretorio está ocupando

    du

Mostra o tamanho em GB

    du -sh

### Mostra uso de disco

    df

### Mostra config de kernel

    uname -a

## Compressão de arquivos

### criar arquivo tar com lista de arquivos

    tar cf arquivos.tar arquivoNomes

### Extrair arquivos de um diretorio

    tar xf arquivo.tar

### Mostra conteudo do arquivos compresso

    tar tf file.tar

Verbosas do comando tar

    c - Cria arquivo
    t - tabela de conteudos
    x - extrai
    z - usa zip/gzip
    f - especifica nome do arquivo
    j - compressão com bzip2
    w - pergunta confirmação
    k - não sobescreve arquivos existentes
    T - lista arquivos comprensados

## Permissões

### Altera permissão do arquivo

    chmod octal file

    4 - ler (r)
    2 - escrever (w)
    1 - Executar (x)

Ordem

    Criador / Grupo / Global

Exemplo

    chmod 777 - rwx para todos
    chmod 755 - rwx para criador, rx para grupo e global

## Outros comandos

Pesquisa padrões de arquivos no diretório

    grep nomeDaBusca

Verbosa

    -r - pesquisar de forma recursiva

Dica de uso

    comandoLinuxPadrão | grep nomeDaBusca

### Localizar arquivos

        locate arquivo

### Mostrar possiveis localizações do app

    whereis app

### Manual do comando

    man comando
