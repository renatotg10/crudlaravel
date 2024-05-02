# Projeto CRUD com Laravel 11

## Preparar Ambiente de Desenvolvimento

### Certifique-se de ter Instalado os Programas:

- PHP
- Composer
- Node.js (NPM)
- MySQL Server
- Visual Studio Code (VS Code)
- BDeaver
- Git
- Criar conta no GITHUB

### Certifique-se de ter Configurado o arquivo `php.ini` confirme abaixo:

#### Habilitar as extensões:

```
extension=zip
extension=fileinfo
extension=curl
extension=gd
extension=mysqli
extension=pdo_mysql
extension=pdo_pgsql
extension=pdo_sqlite
extension=pgsql
extension=sqlite3
extension=mbstring
extension=openssl
```
Sobre as extensões habilitadas:

- **extension=zip**: Esta extensão permite ao PHP trabalhar com arquivos compactados no formato ZIP. Com ela, é possível criar, extrair e manipular arquivos ZIP diretamente no código PHP.

- **extension=fileinfo**: A extensão fileinfo permite ao PHP acessar informações detalhadas sobre arquivos, como tipo MIME, codificação de caracteres e outros detalhes, sem depender apenas da extensão do arquivo ou da sua extensão de nome.

- **extension=curl**: A extensão curl é utilizada para realizar requisições HTTP, FTP, e outras, de forma fácil e eficiente. Ela permite que o PHP interaja com outros servidores, fazendo solicitações e recebendo respostas, o que é fundamental para integração com APIs web, por exemplo.

- **extension=gd**: Esta extensão permite ao PHP manipular imagens, como criar, redimensionar, cortar e aplicar efeitos em imagens. Ela é comumente usada para processamento de imagens dinâmicas em aplicações web, como gerar miniaturas de imagens, aplicar filtros ou criar gráficos.

- **extension=mysqli**: A extensão mysqli (MySQL Improved) é uma melhoria sobre a extensão mysql padrão do PHP, oferecendo uma interface orientada a objetos para interagir com bancos de dados MySQL. Ela é usada para realizar operações de consulta, inserção, atualização e exclusão de dados em bancos de dados MySQL.

- **extension=pdo_mysql**: A extensão pdo_mysql fornece uma interface uniforme para acessar diversos bancos de dados relacionais, incluindo o MySQL, através do PDO (PHP Data Objects). Isso permite que o código PHP seja mais portável entre diferentes sistemas de gerenciamento de banco de dados.

- **extension=pdo_pgsql**: Similar à extensão pdo_mysql, esta extensão pdo_pgsql permite ao PHP interagir com bancos de dados PostgreSQL através do PDO, oferecendo uma camada de abstração para operações de banco de dados.

- **extension=pdo_sqlite**: Esta extensão habilita o suporte do PDO para o SQLite, um banco de dados leve e de fácil integração com aplicações web. O PDO fornece uma maneira consistente de acessar bancos de dados, o que torna o código mais portável.

- **extension=pgsql**: Essa extensão permite ao PHP interagir diretamente com bancos de dados PostgreSQL, oferecendo funções específicas para conectar, consultar e manipular dados em um banco de dados PostgreSQL.

- **extension=sqlite3**: Similar à extensão pdo_sqlite, esta extensão permite ao PHP trabalhar diretamente com bancos de dados SQLite, oferecendo funções específicas para operações como criação de tabelas, inserção de dados, consultas, entre outras.

- **mbstring**: Essa extensão é usada para manipulação de strings multibyte, ou seja, para trabalhar com caracteres multibyte, como os utilizados em vários idiomas além do inglês, como japonês, chinês, coreano, entre outros. Ela oferece funções para lidar com a conversão de encodings de strings, como UTF-8, e manipulação de caracteres multibyte. Isso é útil especialmente quando se trabalha com conteúdo de texto em sites multilíngues.

- **openssl**: Essa extensão fornece uma interface para o OpenSSL, uma biblioteca de software usada para implementar protocolos de segurança, como HTTPS para criptografia de dados em trânsito. A extensão `openssl` permite que o PHP se comunique com servidores usando protocolos seguros, como HTTPS, e também oferece funções para criar e gerenciar chaves criptográficas, certificados SSL/TLS e realizar operações criptográficas, como criptografia e assinatura digital.

#### Habilitar a exibição de erros em tela, o tipo de erro a ser reportado e o registro de logs de erros:

```
display_errors = On
error_reporting = E_ALL
log_errors = On
error_log = /tmp/php_errors.log
```

#### Aumentar o limite de memória (em Mb), bem como o tempo de execução máximo de cada script (em segundos):

```
memory_limit = 256M
max_execution_time = 120
```

#### Permitir o upload de arquivos e aumentar os limites de upload e envio de formulários:

```
session.gc_maxlifetime = 14000
```

## Repositório base desse projeto

Para criação desse projeto foi clonado o repositório **laravel11** da conta Gordin de Óculos do GitHub, que contém
um projeto Laravel 11 com pacote de autenticação Laravel/UI e configurado a notificação personalizada para redefinição de senha.

Link do repositório: https://github.com/gordindeoculos/laravel11

Para clonar o repositório e obter uma cópia do código fonte, foi utilizado o comando:

```
git clone https://github.com/gordindeoculos/laravel11
```

## Criar o Repositório Git

1. Foi renomeado a pasta do projeto clonado de `laravel11` para `curd-laravel`. Para isso, foi utilizado o comando:

```
rename laravel11 crud-laravel
```

2. Foi excluído a pasta `.git` com o comando:

```
rmdir .git /q /s
```

3. Criado o conteúdo para o arquivo `.gitignore` através do link https://gitignore.io com os parametros `windows`, `visualsturiocode` e
`laravel`.

4. Inicializado novo repositório Git para esse projeto com os comandos:

```
git init
git add .
git commit -am "Inicio do Projeto"
```

### Configurar o ambiente de desenvolvimento e instalar as dependências do projeto

Como foi feito o clone do projeto Laravel a partir do GitHub, é necessário executar os comandos abaixo para configurar o
ambiente de desenvolvimento e instalar as dependências do projeto.

1. **Instalar as dependências do projeto**:
   No diretório do projeto Laravel clonado, execute o seguinte comando no terminal:

   ```
   composer install
   ```

   Isso instalará todas as dependências do Laravel listadas no arquivo `composer.json`.

Sim, se o projeto Laravel incluir recursos front-end que dependem do Node.js e do npm (como o Laravel Mix para compilação de assets), você precisará executar os comandos `npm install` e `npm run build` para para compilar e combinar arquivos JavaScript e CSS.

Aqui está o que cada comando faz:

2. **npm install**:
   Este comando instala todas as dependências listadas no arquivo `package.json` do projeto. Isso inclui todas as bibliotecas JavaScript necessárias para o desenvolvimento, como Vue.js, Bootstrap, jQuery, etc., bem como quaisquer ferramentas de compilação e construção, como Laravel Mix.

   ```
   npm install
   ```

3. **npm run build**:
   Este comando compila e otimiza os assets do front-end do seu projeto para produção. O Laravel Mix, que é uma camada sobre o webpack, geralmente é usado para compilar e combinar arquivos JavaScript e CSS. O comando npm run build executa a compilação e otimização dos assets para um ambiente de produção.

   ```
   npm run build
   ```

4. **Copiar o arquivo de ambiente**:
   O Laravel utiliza um arquivo `.env` para armazenar variáveis de ambiente como configurações de banco de dados, chaves de API, etc. Faça uma cópia do arquivo `.env.example` e renomeie-a para `.env`.

   ```
   copy .env.example .env
   ```

5. **Configurar o arquivo `.env`**:
   Abra o arquivo `.env` e configure as variáveis de ambiente, como conexão com o banco de dados, chaves de API, etc., de acordo com o seu ambiente de desenvolvimento.

6. **Criar o arquivo `database.sqlite`**:
   Se o seu projeto Laravel estiver configurado para usar o SQLite como banco de dados, você precisará criar o arquivo `database/database.sqlite` manualmente, pois o SQLite é um banco de dados baseado em arquivo.

   Para criar o arquivo `database.sqlite`, você pode simplesmente criar um arquivo vazio com esse nome na pasta `database` do seu projeto Laravel. Você pode fazer isso manualmente ou através do terminal usando comandos como `touch` ou `type nul >`.

   Por exemplo, no terminal do Windows, você pode fazer o seguinte:

   ```
   cd database
   type nul > database.sqlite
   ```

   Depois de criar o arquivo `database.sqlite`, o Laravel poderá usar SQLite como banco de dados e você poderá executar as migrações e outras operações de banco de dados normalmente.

6. **Gerar uma nova chave de aplicativo**:
   Execute o seguinte comando para gerar uma nova chave de aplicativo para sua aplicação Laravel:

   ```
   php artisan key:generate
   ```

8. **Executar as migrações do banco de dados (se necessário)**:
   Se o projeto Laravel incluir migrações para o banco de dados, você precisará executá-las para criar a estrutura do banco de dados. Execute o seguinte comando:

   ```
   php artisan migrate
   ```

   Isso irá criar as tabelas no banco de dados de acordo com as migrações fornecidas.

7. **Iniciar o servidor de desenvolvimento**:
   Para iniciar o servidor de desenvolvimento do Laravel, execute o seguinte comando:

   ```
   php artisan serve
   ```

   Isso iniciará um servidor local para o seu aplicativo Laravel, normalmente em `http://localhost:8000`.

Depois de seguir esses passos, seu ambiente de desenvolvimento Laravel no Windows estará configurado e pronto para uso.

## Referências



