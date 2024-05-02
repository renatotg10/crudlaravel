# Projeto CRUD com Laravel 11

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



