# Criar package.json

	npm init -v	

### Instalar fastify, TS

	npm i fastify

	npm i typeScript -D

	npx tsc --init

### Instalar Prisma - ORM

	npm i -D prisma

	npm i @prisma/client


### Instalar cors (responsavel pela segurança. Indica quais serviços podem acessar a api)

	npm i @fastify/cors

### Iniciar Prisma - A flag datasource indica qual BD q vai ser utilizado

	npx prisma init --datasource-provider SQLite

### Manipulação de datas

	npm i dayjs



### Criar pasta src dentro da pasta do projeto e Criar arquivo server.ts


### No arquivo package.json
### Na linha dev, dentro de scripts, alterar a linha para

	"scripts": {
		"dev":"tsx watch src/server.ts"
	}




# No arquivo server.ts
### Importar fastify (responsavel pelas rotas da API)

	import Fastify from 'fastify'

### Import da ORM prisma para operaçõs com BD

	import {PrismaClient} from '@prisma/client'

### Importar cors para segurança

	import cors from '@fastify/cors'


### Instanciar variavel responsavel pela criação das rotas

	const app = Fastify()

### Instanciar variavel responsavel pelas operações com o/a BD - ORM

	const prisma = new PrismaClient()

## Setar quais aplicações podem acessar a API

	app.register(cors, {
		origin: ['http:#localhost:3333']
	})




# Primeira rota do projeto 
### Metodo get o qual retorna uma informação / view / etc
### get, post, delete, put, patch

### Exemplo de Rota

	app.get('/', async ()=>{
		const nomeQuery = await prisma.nomeTabela.findMany({
			where:{
				dado:{
					startsWith: 'INFORMAÇÃO'
				}
			}
		})
		return nomeQuery
	})

## Responsavel por inicializar o servidor

	app.listen({
		port:3333
	}).then(()=>{
		console.log('Server Rodando')
	})

