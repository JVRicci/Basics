# Criar package.json

	npm init -v	

### Instalar fastify, TS

	npm i fastify

	npm i TypeScript -D

	npx tsc --init

### Instalar Prisma - ORM

	npm i -D prisma

	npm i @prisma/client


### Instalar cors (responsavel pela segurança. Indica quais serviços podem acessar a api)

	npm i @fastify/cors

### Iniciar Prisma - A flag datasource indica qual BD q vai ser utilizado

	npx prisma init --datasource-provider SQLite


### Criar pasta src dentro da pasta do projeto e Criar arquivo server.ts


### No arquivo package.json
### Na linha dev, dentro de scripts, alterar a linha para

	"scripts": {
		"dev":"tsx watch src/server.ts"
	}



