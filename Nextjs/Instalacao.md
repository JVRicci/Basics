## Criação do projeto

    npx create-next-app@latest

## Instalação do ESLint

    npm eslint --init

Para configuração é necessário também incluir alterações também no arquivo .eslintrc.json
Essas alterações são encontrasas [aqui](https://www.npmjs.com/package/eslint-plugin-react-hooks)

## Instalar Prettier

    npm install prettier eslint-config-prettier -D

## Lib para testes Jest

    npm install --save-dev jest
    npm install --save-dev @testing-library/react jest-environment-jsdom @testing-library/jest-dom @swc/jest @types/jest
