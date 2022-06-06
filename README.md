# Multi-Stack-Back-PHP
💻 [Repositório - GitHub](https://github.com/treinaweb/workshop-multistack-adote-um-pet-php)

## Checklist do Ambiente

- [ ]  Instalar PHP
- [ ]  Instalar Composer
- [ ]  Instalar Visual Studio Code
- [ ]  Instalar DBeaver
- [ ]  Instalar Insomnia

📎 [Instruções de configuração - Windows](https://www.treinaweb.com.br/blog/configurando-o-ambiente-de-desenvolvimento-php-laravel-no-windows)

📎 [Instruções de configuração - Linux](https://www.treinaweb.com.br/blog/configurando-o-ambiente-de-desenvolvimento-php-laravel-no-linux)

📎 [Instruções de configuração - macOS](https://www.treinaweb.com.br/blog/configurando-o-ambiente-de-desenvolvimento-php-laravel-no-macos)

## Checklist da Criação do Projeto

- [ ]  Criar o projeto
    
    `composer create-project laravel/laravel adote-um-pet`
    
- [ ]  Iniciar o servidor de desenvolvimento
    
    `php artisan serve`
    

## Checklist da primeira aula de Laravel

**Endpoint de Lista de Pets**

- [ ]  Criar arquivo de controller PetController
    
    `php artisan make:controller PetController`
    
- [ ]  Configurando o banco de dados SQLite
- [ ]  Criar arquivo de migration de Pet
    
    `php artisan make:migration create_pets_table`
    
- [ ]  Código dos campos da migração de Pet
    
    ```php
    $table->string('nome', 50);
    $table->text('historia');
    $table->string('foto', 1000);
    ```
    
- [ ]  Executar migrações no banco de dados
    
    `php artisan migrate`
    

**Endpoint de registro de adoção**

- [ ]  Criar arquivo de controller AdocaoController
    
    `php artisan make:controller AdocaoController`
    
- [ ]  Criar arquivo de migration de Adoção
    
    `php artisan make:migration create_adocoes_table`
    
- [ ]  Código dos campos da migração de Adoção
    
    ```php
    $table->string('email', 100);
    $table->decimal('valor');
    
    $table->unsignedBigInteger('pet_id');
    $table->foreign('pet_id')->references('id')->on('pets');
    ```
    
- [ ]  Executar migrações no banco de dados
    
    `php artisan migrate`
    
- [ ]  Criar modelo Adocao
    
    `php artisan make:model Adocao`
    
- [ ]  Código atributo `fillable` no modelo Adocao
    
    ```php
    protected $fillable = ['pet_id', 'email', 'valor'];
    ```
    

## Checklist da segunda aula de Laravel

- [ ]  Iniciar o servidor de desenvolvimento
    
    `php artisan serve`
    
- [ ]  Código atributo `fillable` no modelo Adocao
    
    ```php
    protected $fillable = ['nome', 'historia', 'foto'];
    ```
    
- [ ]  Criar a camada de FormRequest para validação do Pet
    
    `php artisan make:request PetRequest`
    
- [ ]  Criando API Resources da adoção
    
    `php artisan make:resource AdocaoResource`
    
    `php artisan make:resource AdocaoCollection`
    
- [ ]  Instalar o pacote de tradução para pt_BR
    
    `composer require lucascudo/laravel-pt-br-localization --dev`
    
    `php artisan vendor:publish --tag=laravel-pt-br-localization`