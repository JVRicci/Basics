# No arquivo server.ts
## Importar fastify (responsavel pelas rotas da API)

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
#Exemplo de Rota

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
