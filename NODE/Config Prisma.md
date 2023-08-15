
## Configuração inial do prisma para o editor
Pressionando o ctrl + t, no preferences.json, adcionar as seguintes linhas

	"[prisma]": {
	"editor.defaultFormatter": "Prisma.prisma"
	},


## Acesso as tabelas visualmente

	//Para instalação do package
	npm i -D prisma-erd-generator @mermaid-js/mermaid-cli

	//É necessário adcionar as seguintes linhas no arquivo schema.prisma
	generator erd {
		provider = "prisma-erd-generator"
	}

	//Para gerar as tabelas visuais
	npx prisma generate

###  Criação de models: dentro de schema.prisma

	model nomeTabela{
		id		String @id @default (uuid())
		title		String
		created_at	DateTime
	}


### Criar e rodas migrations
	
	npx prisma migrate dev 

###  Com isso, no terminal irá solicitar o nome da operação. Ex:

	create table nomeTabela

### Abrir interface da DB do prisma

	npx prima studio


### Preencher a base de dados com seed

No link tem o código e instruções, para criação de um seed para preenchimento do bando ce dados

https://www.prisma.io/docs/guides/database/seed-database

### Copiar base de dados já existente para model do prisma
Primeiramente é necessário confirmar que no arquivo .env está com a configuração correta do banco
Se o caminho está correto. É necessário conferir na documentação a estrutura de cada tipo de banco
Documentação exata [aqui](https://www.prisma.io/docs/reference/database-reference/connection-urls)

Após isso é necessário apenas usar o seguinte comando

	npm prisma db pull

Com isso todas as bases são geradas automaticamente