## Passos inicias para criação de projetos

    composer create-project laravel/laravel NOME_DO_PROJETO

## Scafolding de Auth do UI

    composer require laravel/ui  
    php artisan ui react
    php artisan ui react --auth   

    npm i --force
    npm run dev

## Gerar BD

Altere o nome do BD no .env, e depois rode o comando

    php artisan migrate

## Passos iniciais para projeto já existente

    composer update
    composer install
    
    npm install
    npm run dev

## Para iniciar o projeto é necessário antes usar o seguinte comando 

    composer dump-autoload

## Alternativa com force

    composer i --ignore-platform-reqs

## Instalar Debugbar

    composer require barryvdh/laravel-debugbar --dev

## Assim que estiver tudo pronto:
### Criar arquivo .env e alterar o nome do banco, login e senha de acesso
### Assim que estiver tudo pronto, utilizar o seguinte comando para rodar as migrations

    php artisan key:generate
    php artisan migrate

### Para Startar

    php artisan serve

### Terminal do php para comandos e Base de Dados

    php artisan tinker


#### Obs: Sempre observar se a variavel de ambiente do php está correta


##### Criar scaffolding jetstream para auth dentre outros

    composer require laravel/jetstream
    php artisan jetstream:install livewire --teams