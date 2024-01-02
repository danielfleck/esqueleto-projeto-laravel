# PROVISIONAMENTO DE AMBIENTE COM PHP, POSTGRES E REDIS

Pretende reduzir as dificuldades para criação e versionamento de configuração de ambientes. 

Permite registrar, efetivamente, os módulos e configurações que deverão ser replicadas para o ambiente de produção ao longo do projeto.

## UTILIZAÇÃO

Após inicializar o diretório de trabalho do sistema e configurar o repositório git, fazer o download do arquivo ```zip``` do projeto e descompactar dentro do projeto em um pasta chamada docker. 

Não convém clonar o repositório pois o objetivo é justamente ambiente versionar do projeo através do repositório *git* do sistema e não mais do projeto do ambiente.

Se houver colisão das portas dos containeres com as portas locais, fazer uma cópia do arquivo ```.env.exemplo```para ```.env``` e editar. O docker composer lerá o arquivo automaticamente.

As portas que serão usadas poderão ser diferentes em cada máquina por isso não deve fazer parte do versionamento.

Os comandos do docker deverão ser efetuados dentro do diretório docker.

### Comando para iniciar os containeres:

```bash
$ docker compose up -d
$ docker compose --env-file=.env up -d # para forçar ler o arquivo contendo a indicação das portas dos serviços
```

**Caso alguma dessas portas: 80, 443, 5432, 6379, esteja
sendo utilizada no host, irá gerar um erro. O arquivo
```.env``` deverá ser editado para indicação de outras
portas.**

### Comando para parar os containeres:

```bash
$ docker compose down
```

**Caso sejam feitas alterações nas configurações das
imagens, ou seja, em qualquer arquivo da pasta docker,
as imagens precisam ser reconstruídas:**

```bash
$ docker compose up --build -d
$ docker compose --env-file=.env up --build -d # para forçar ler o arquivo contendo a indicação das portas dos serviços
```

Esse último procedimento pode demorar mas não precisa ser realizado com frequência.

### Comando para acesssar o shell dos containeres

> Obs.: os comnandos docker devem ser executados dentro do diretório docker.

```bash
# bash em app (php)
$ docker compose exec app "/bin/bash"

# bash em db
$ docker compose exec db "/bin/bash"

# bash em redis
$ docker compose exec redis "/bin/bash"
```

### Comando para acessar o prompt de comando psql em db

> Obs.: os comnandos docker devem ser executados dentro do diretório docker.

```bash
#      app: é o nome do usuário que consta em .env
# postgres: é o nome do banco de dados que será conectado
$ docker compose exec db psql -U app postgres
```

## APP (PHP)

O arquivo ```Dockerfile``` do diretório app apresenta as principais configurações do ambiente, como: ```php.ini``` de *dev.* e *prod.* e os módulos indicados para cada ambiente.

Há um diretório ```conf.d-dev``` onde as configurações exclusivas de desenvolvimento devem ser inclulídas.

No diretório ```conf.d-prod``` devem ser inseridas todas as configurações indispensáveis ao ambiente de produção. Essas configurações estarão disponíveis no ambiente de desenvolvimento.

Para tornar o módulo disponível no ambiente, basta descomentar a linha com o comando ```RUN``` dentro do arquivo ```Dockerfile```. Assim é possível identificar de forma prática os módulos realmente necessários para execução da aplicação.

O arquivo ```php.ini``` pode ser personalizado para o ambiente de desenvolvimento e de produção. O objetivo é poder identificar as configurações que foram feitas no ```php.ini``` ao longo do projeto.

Os arquivos de configurações básicas de *virtualhost* do *Apache* estão na pasta ```vhosts```. As chaves *SSL* do *vhost* são criadas e autoassinadas durante a criação da imagem.

Nas configurações da imagem de desenvolvimento consta a instalação do *Composer*, *Node*, *Yarn* e Symfony CLI.

## DB (POSTGRESQL)

O arquivo ```Dockerfile``` apresenta a instalação padrão da última versão do Postgresql.

Está disponível, através da remoção de comentários no arquivo ```Dockerfile``` a possibilidade de instalação de dois módulo do *Postgresql*: *Postgis* e *FDW*.

Na pasta ```arquivos``` existe o exemplo de arquivos com comandos para criação e manipulação de bancos de dados na imagem.

## REDIS

O arquivo ```Dockerfile``` apresenta a instalação padrão da última versão do Redis.

O arquivo de configuração está disponível para ajustes.
