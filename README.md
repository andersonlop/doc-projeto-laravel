# Documento para Criação de Projetos Laravel
Passo a Passo para criar forms e projetos em Laravel

## Requisitos

* PHP 8.2 ou superior
* Composer
* Node.js 20 ou superior
* GIT

# CRIANDO O PROJETO

## 1 - Criação do Banco
Entrar no **PhpMyadmin** e criar o banco com o nome **nome_do_projeto**

# 2 - Criar o projeto com Laravel

```
composer create-project laravel/laravel nome-do-projeto
```

# CONFIGURANDO O PROJETO

## Configuração .env
Neste item vamos fazer a Configuração o arquivo **.env**, faça os procedimentos abaixo:

### 1 - Configuração do Nome do Projeto
Abra o arquivo **.env** Configure o Nome do Projeto usando a variável **APP_NAME**

## 2 - Configuração do Banco de Dados
Faça as devidas configurações do Banco de Dados, nas variáveis abaixo:

**DB_CONNECTION=mysql

**DB_HOST=127.0.0.1 // Aqui você configura o servidor do Banco de Dados

**DB_PORT=3306 // Aqui você configura a porta do Banco de Dados

**DB_DATABASE=nome-banco // Aqui você configura o nome do Banco de Dados

**DB_USERNAME=root // Aqui você configura o Nome do Usuário do Banco de Dados

**DB_PASSWORD= //Aqui você configura a senha do banco de dados, se vc instalou o Xampp, a senha padrão é vazio


## Configuração config/app
Abra o arquivo **config/app** e faça as configurações de **timezone** e **locale**, se não conseguir siga os passos abaixo:

### 1 - timezone
Abra o arquivo **config/app** e procure por **timezone**, em seguida configure de acordo com a sua necessidade, ex: **'timezone' => 'America/Sao_Paulo'**

### 2 - locale
Ainda no arquivo **config/app** Configure o locale de acordo com sua necessidade, ex: **'locale' => 'pt_BR'**

## Tradução do Laravel
Caso você queira fazer a tradução das mensagens do Laravel, siga os passo abaixo:

### 1 - Comando 1
```
composer require lucascudo/laravel-pt-br-localization --dev
```

### 2 - Comando 2
```
php artisan vendor:publish --tag=laravel-pt-br-localization
```

## Criação do Helper
Crie um arquivo de helper para sua aplicação, o helper é importante para você personalizar funções específicas do seu projeto, caso não saiba como fazer siga as orientações abaixo:

### 1 - Criação do Arquivo helpers.php
Crie uma pasta chamada Helper dentro de app e em seguida <a href="https://drive.google.com/file/d/11hChm426c2DiavXsvUj_bVH1xiRCcLeR/view?usp=sharing" target="_blank">**baixe aqui o arquivo**</a> e coloquei dentro desta pasta.

### 2 - Registro no Composer.json
Registre o helper no autoload do composer arquivo **composer.json**

```
"files" : [
   "app/Helper/helpers.php"
 ],
 ```

### 3 - Atualização do Composer

Atualize o composer usando o comando: 
 ```
composer update
 ```

 ## Outros Passos
 Outros comandos de configuração

 ### 1 - Biblioteca de Validação
 
Caso ache interessante para seu projeto instale a biblioteca de Validação para o seu projeto, caso não saiba como siga os passos abaixo:
```
composer require laravellegends/pt-br-validator
```

### 2 - Constantes para status
<a href="https://drive.google.com/file/d/1pVtfswF5Ll3vxHKU8VSMcJrN4Ud1f281/view?usp=sharing" target="_blank">**Baixe aqui**</a> o arquivo e coloque dentro da pasta **config**.

### 3 - Arquivo UtilService
Crie a pasta **Service** dentro da pasta **app**, depois dentro da pasta Service crie o arquivo **UltilService.php** e implemente a classe.

```
<?php

namespace App\Service;

class UtilService{
    
}
```