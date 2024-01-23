# Documento para Criação de Projetos Laravel
Passo a Passo para criar forms e projetos em Laravel 10

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

# BAIXANDO O LAYOUT
Encontre na internet um layout que agrade.

## 1 - Criando as Views Necessárias
Dentro da Pasta **resources/views** crie **04 arquivos**, sendo eles:

**- cabecalho.blade.php**
**- home.blade.php**
**- menu.blade.php**
**- template.php**

**Obs:** Pode ser criado mais de acordo com o seu projeto.

## 2 - Criando o HomeController

### 1 - Comando
```
php artisan make:controller HomeController
```

### 2 - Método Index
```
public function index(){
        return view("home");
    }
```

## 3 - Criando a rota home
```
Route::get('/', [HomeControlller::class, "index"] )->name("home");
```

## 4 - Copiando a pasta inc
Copie a pasta inc (que está no arquivo que foi baixado) para a pasta **resources/views**.

## 5 - Copiando os arquivos de recursos
Dentro da pasta public crie uma pasta chamada assets e dentro dela copie as pastas:

**- componentes**
**- css**
**- img**
**- js**

# FATIANDO LAYOUT - PARTE 01

## 1 - Instruções gerais
Para fatiar o layout é importante observar a estrutura html do arquivo index do layout baixado e verificar dentro desta estrutura o que representa a página home, o cabecalho, rodapé, menu, etc. Desta forma, abra o arquivo index do layout que foi baixo e faça os procedimentos abaixo:

- abra o arquivo template.blade.php que está dentro da pasta resources/views

- Copie o conteúdo do arquivo index do layout baixado para o arquivo template.blade.php

-Para que os recursos possam ser visualizados no layout é necessário setá-los, ou seja, informar o caminho completo dos recursos e para isso vamos usar a função asset e informar com caminho completo dos recursos.

- Sete todos os recursos necessários do arquivo template para que possa linkar o css, imagem e js e em seguida rode o projeto.

## 2 - Cabeçalho
Crie um arquivo chamado cabecalho.blade.php dentro da pasta resources/views, em seguida faça os procedimentos abaixo:


- Do arquivo template recorte o conteúdo que você considera fazer parte do cabeçalho do projeto
- Abra o arquivo cabecalho.blade.php e cole o conteúdo recortado
- No arquivo index no local onde estava o conteúdo que foi recortado para o cabecalho faça um include ao arquivo cabecalho

## 3 - Menu
Para configurar o arquivo menu, façamos o seguinte procedimento:

- Crie um arquivo chamado cabecalho.blade.php dentro da pasta **resources/views**:
- no arquivo template recorte o conteúdo que você considera fazer parte do menu do projeto
- Abra o arquivo menu.blade.php e cole o conteúdo recortado
- No arquivo index no local onde estava o conteúdo que foi recortado para o menu faça um include ao arquivo cabecalho

## 4 - Home 
Para configurar o arquivo home, façamos o seguinte procedimento:

- Crie um arquivo chamado home.blade.php dentro da pasta resources/views:
- no arquivo template recorte o conteúdo que você considera fazer parte do home do projeto
- Abra o arquivo home.blade.php, crie a marcação

## 5 - Template
O arquivo template representa a estrutura fixa do sistema que envolverá todas as views, teoricamente seria o conteúdo do arquivo index, excluindo a parte que foi tirada para o cabeçalho, o menu e home.

no template também iremos configurar os recursos principais do projeto como o css e o javascript e outras bibliotecas necessárias.

Para tornar o layout dinâmico, precisamos ajustar o include do home da seguinte forma:

Ao invés de incluir o arquivo diretamente pelo include iremos chamar o método @yield passar como parâmetro a palavra 'conteudo',
ficando: @yield('conteudo')

Modifique o arquivo template implementando o código acima.

## 6 - Rodando o projeto
Ajuste seu projeto de forma que consiga renderizar todas as imagens, css, javascript e em seguida execute.


# CRIANDO O FORMULÁRIO

## 1 - Criando o Model

```
```
