## Passos iniciais

    npm i
    composer update
    composer install

## Para iniciar o projeto é necessário antes usar o seguinte comando 

    composer dump-autoload

## Alternativa com force

    composer i --ignore-platform-reqs

## Instalar Debugbar

    composer require barryvdh/laravel-debugbar --dev

## Assim que estiver tudo pronto:
### Criar arquivo .env e alterar o nome do bando, login e senha de acesso
### Assim que estiver tudo pronto, utilizar o seguinte comando para rodar as migrations

    php artisan key:generate
    php artisan migrate

### Para Startar

    php artisan serve

### Terminal do php para comandos e Base de Dados

    php artisan tinker


#### Obs: Sempre observar se a variavel de ambiente do php está correta