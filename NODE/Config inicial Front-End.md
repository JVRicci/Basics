### Iniciar projeto com vite

#### Cria o projeto como vanilla, ou com frameworks e libs como React e Vue

#### Possibilidade de criar projeto em branco, ou com inicio em TS ou JS

    npm create vite@latest

### Instalar Tailwind CSS (framework para css)

    npm install -D tailwindcss postcss autoprefixer

    npx tailwind init -p

Lib util para tailwind (Opicional)

    npm i -D daisyui@latest

## Lib que permite condicionais com style.

    npm i clsx

### Instala de fato as dependencias

    npm install

### Startar projeto no browser

    npm run dev

### Criar arquivo global.css dentro da pasta src/styles

### Nela, escrever, para o funcionamento do tailwind

    @tailwind base;
    @tailwind utilities;
    @tailwind components;

### Dentro de app.tsx

    import './styles/global.css'

### Dentro de tailwind.config. Isso indica os arquivos que leem o tailwind

    content:{
    	'./src/**/*.tsx',
    	'./index.html'
    }

### Lib para icones do react

    npm i phosphor-react

### Instalção do Radix para criação de ferramentas como popover, modal, etc

    npm install @radix-ui/react-dialog
    npm install @radix-ui/react-dropdown-menu
    npm install @radix-ui/react-tooltip

## Instalar clerk para authentication no sistema

    npm install @clerk/clerk-js

## Usando Axios para requisição

#### Inicialmente é necessário intalar a lib

    npm i axios

#### Após isso, basta criar uma pasta chamada lib (a qual é util para armazenar arquivos relacionados a libs, n somente axios)

#### Dentro dessa pasta, deve ser criado um arquivo chamado axios com a seguinte configuração

    import axios from "axios"

    export const api = axios.create({
    	baseURL: 'http://nomeDaUrl:3333'
    })

#### Para utlizar, basta importar o arquivo com

    import { api } from '../lib/axios'

#### A variavel api terá acesso a comandos como get, post, etc. _Ver na documentação_

---

### Lib para Icons em geral

Essa lib tem icons de diversas libs
Para usala basta importar 'react-icons/NOME_DA_FONTE'

    npm i react-icons

---

### Utilizando Styled Components

Basta apenas instalar os seguintes pacotes

    npm i styled-components
    npm i @types/styled-components

A partir disso, é criado um arquivo global na pasta styles

    import { createGlobalStyle } from "styled-components";


    export default createGlobalStyle`
    	*{
    		margin:  0;
    		padding: 0;
    		outline: 0;
    		box-sizing: border-box;
    	}

    	html, body, #root{
    		height:100%;    /*altura da página*/
    	}

    	body{
    		font-family: 'roboto', sans-serif;
    		background-color: #ecf1f8;
    		color: #333;
    		/* Suaviza a fonte, não deixando ela pixelizada */
    		-webkit-font-smoothing: atialiased !important;
    	}

    `;

Esse arquivo será aplicado a toda aplicação

---

# Criação de id unicos

No caso de react por exemplo, seu uso é interessante para criação de keys em maps()

    npm i uuidv4

Implementação / Importação

    import { uuid } from "uuidv4"

Função que gera UUID

    uuid()
