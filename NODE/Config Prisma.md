

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