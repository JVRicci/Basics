### Iniciar projeto com vite
#### Cria o projeto como vanilla, ou com frameworks e libs como React e Vue
#### Possibilidade de criar projeto em branco, ou com inicio em TS ou JS

	npm create vite@latest


### Instalar Tailwind CSS (framework para css)

	npm install -D tailwindcss postcss autoprefixer

	npx tailwind init -p

## Instalar Lib para ferramentas como Modals, Popovers dentre outros

	npm install @radix-ui/react-dialog
	npm install @radix-ui/react-dropdown-menu
	npm install @radix-ui/react-tooltip

## Lib que permite condicionais com style. Ex: 
#### className={clsx('w-10 h-10 bg-zinc-900 border-2 border-zinc-800 rounded-lg',
#### {
####	'bg-violet-900 border-zinc-800': completedPercentage === 0,
#### }}

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

	mport './styles/global.css'

### Dentro de tailwind.config. Isso indica os arquivos que leem o tailwind

	content:{
		'./src/**/*.tsx',
		'./index.html'
	}

### Lib para icones do react

	npm i phosphor-react
