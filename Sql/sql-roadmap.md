# Roadmap de estudos de SQL

**Aviso**: Muitas vezes detalhes de várias operações podem variar de banco para banco. Em questões onde fiquei
em dúvida, este documento segue o funcionamento do PostgreSQL, pois é o banco que conheço melhor.

## Pré-requisito: Álgebra Relacional básica
Antes de começar a escrever SQL, você precisa entender o modelo de
como um banco de dados relacional funciona. Não precisa se aprofundar
muito, mas você precisa entender como que dados e relacionamentos entre
eles são representados. (Nota importante: Relacionamento e relação não são a
mesma coisa!)

Coisas que você precisa saber responder:
- O que é uma relação?
- Como dados são representados em uma relação?
- Como podemos expressar relacionamentos entre relações distintas?

Você vai ver um monte de operações matemáticas complexas estudando isso.
Não se preocupe demais, a este ponto você só precisa entender a lógica geral.

## Nível Básico
### Buscando dados
O ideal é começar com um banco de dados já predefinido e aprender a buscar dados
de várias formas nele. Você pode usar bancos já prontos para aprendizado como o https://mystery.knightlab.com/
ou pegar datasets como os que tem aqui: https://learnsql.com/blog/free-online-datasets-to-practice-sql/

O que você precisa aprender nessa fase:
- Filtrar as linhas de uma tabela usando `WHERE`
- Remover linhas duplicadas usando `DISTINCT`
- Combinar condições usando `AND`, `OR` e `NOT`
- Ordenar os resultados usando `ORDER BY`
- Limitar a quantidade de resultados usando `LIMIT` ou `TOP`
- Filtrar strings usando `LIKE`

### Atualizando dados
O que você precisa aprender nessa fase:
- Atualizar dados no banco usando `UPDATE`
- Apagar dados do banco usando `DELETE`

### Fazendo agregações nos dados selecionados
O que você precisa aprender nessa fase:
- Selecionar dados agregados usando `COUNT()`, `AVG()`, `SUM()`, `MIN()` e `MAX()`
- Agrupar linhas usando `GROUP BY` e colcular agregações sobre cada grupo

## Nível Básico+
Agora que você aprendeu a buscar e atualizar dados, é a hora de começar a modelar
seus próprios dados. Tem vários exemplos clássicos, mas o ideal é você tentar modelar
algo que seja interessante pra você ou tentar fazer algo baseado nos datasets de exemplo
que mandei acima.

### Modelagem relacional
O que você precisa aprender nessa fase:
- Aprender como pegar dados estruturados e convertê-los em um modelo relacional normalizado.
  Você pode usar recursos como o [Guia de normalização do TowardsDataScience](https://towardsdatascience.com/a-complete-guide-to-database-normalization-in-sql-6b16544deb0)
- Aprender sobre chaves primárias e chaves estrangeiras
- Praticar a modelagem criando schemas SQL usando `CREATE TABLE`
- Aprender a inserir dados usando `INSERT`
- Aprender a gerenciar as tabelas do seu banco usando `ALTER TABLE` e `DROP TABLE`

### Constraints
Em geral, você quer impor restrições sobre os dados que entram no banco. Em geral é melhor
impedir dados inválidos de entrarem no banco com constraints e não deixar o controle disso
só na aplicação que acessa o banco.

O que você precisa aprender nessa fase:
- Impedir valores duplicados em tabelas com o constraint `UNIQUE`
- Impedir valores nulos em colunas com o constraint `NOT NULL`
- Aplicar condições arbitrárias sobre dados com o constraint `CHECK`

### Selecionando de múltiplas tabelas
Até agora você estava selecionando dados de uma tabela só, mas no mundo real muitas vezes
precisamos encontrar dados de várias tabelas. Por exemplo, em um sistema de venda de passagens,
encontrar as passagens compradas por um determinado usuário.

O que você precisa aprender nessa fase:
- Juntar os dados em comum de tabelas usando `INNER JOIN`
- Selecionar os dados de uma tabela que estão presentes em outra usando `LEFT JOIN` e `RIGHT JOIN`
- Combinar tabelas usando `FULL OUTER JOIN`
- Selecionar dados hierárquicos e fazer comparações usando self-joins

### Organizando queries
Com JOIN, suas queries vão começar a ficar bastante complexas. Para organizá-las, você pode separá-las
em fragmentos reutilizáveis utilizando Common Table Expressions.

O que você precisa aprender nessa fase:
- Usar os resultados de uma query em outra com subqueries
- Compor queries complexas a partir de fragmentos simples usando `WITH`
- Aprenda a diferença entre CTEs e subqueries e por que em geral é melhor usar CTEs

## Nível Intermediário
Você já sabe a maior parte das features necessárias para compor queries complexas.
Agora iremos estudar algumas operações mais exóticas e como manter a integridade de dados
do seu banco quando ele é consultado por uma aplicação.

### Operações menos comuns
O que você precisa aprender nessa fase:
- Juntar os resultados de várias queries usando `UNION`, `INTERSECTION` e `EXCEPT`
- Criar condicionais usando `CASE`
- Tratar valores nulos usando `COALESCE` e `NULLIF`
- Fazer comparações com listas de valores usando `ANY`, `ALL` e `EXISTS`

### Teoria: ACID
O que você precisa aprender nessa fase:
- O que é cada uma das propriedades da sigla ACID
- Como os bancos SQL garantem as propriedades ACID

### Índices
Índices servem para acelerar queries sobre campos específicos. Você pode usar índices
para acelerar a execução de queries frequentes. Recomendo ler os primeiros capítulos do
[Use the Index, Luke!](https://use-the-index-luke.com/).

### Transações
Muitas vezes você precisa fazer várias queries de escrita e possivelmente de leitura no banco
de forma tal que, se uma delas falha, o banco deve ficar no estado inicial. Isso é possível
em SQL usando transações - blocos de queries associadas entre si.

**Este é um tópico que varia bastante entre implementações de bancos de dados.**

O que você precisa aprender nessa fase:
- Criar, confirmar e cancelar transações usando `BEGIN`, `COMMIT` e `ROLLBACK`
- Aprender sobre os níveis de isolamento de transações
- Estudar quais garantias o seu banco dá em cada nível de isolamento disponível nele
- Aprender a usar transações junto com constraints para garantir segurança de forma eficiente
- Praticar bastante usar transações, especialmente em situações de vários acessos simultâneos

### Locking
É relativamente comum precisar ler um dado na aplicação, fazer alguma operação com ele
e escrever de volta no banco de dados. Isso pode causar problemas se o valor desse dado
for alterado entre a leitura e a escrita. Para impedir isso, é possível trancar partes do
banco de dados para que ele não possa ser modificado até que alguma condição seja satisfeita.

**Este é um tópico que varia bastante entre implementações de bancos de dados.**

O que você precisa aprender nessa fase:
- Antes de estudar locking, aprenda a evitar locking com `UPDATE`s bem planejados! Locking
  **sempre** tem um custo de performance e deve ser evitado sempre que possível.
- Trancar dados que serão escritos posteriormente usando `SELECT FOR UPDATE` ou `UPDLOCK`.
- Aprenda quais são os níveis de locking que seu banco oferece e as diferenças entre eles.
- Aprenda a fazer "locking otimista" usando um campo de versionamento na tabela.

### Funções built-in
Em geral servidores SQL oferecem várias funções para manipular dados mais complexos como datas, números,
tipos compostos, etc.

**Este é um tópico que varia bastante entre implementações de bancos de dados.**

O que você precisa aprender nessa fase:
- Aprenda quais são os tipos de dados do seu banco. Você provavelmente aprendeu o básico
  modelando tabelas, mas você sabia que, por exemplo, o Postgres tem uma série de tipos específicos
  pra fazer queries sobre dados geométricos, como por ex determinar se um conjunto de coordenadas está
  dentro de uma determinada área?
- Aprenda a converter entre tipos de dados com `CAST`
- Para cada um dos tipos, pesquise as funções que seu banco oferece para tratá-lo. 
- Em especial, aprenda os operadores de datas! É extremamente comum precisar fazer coisas como computar
  uma data a partir de dia, mês e ano, ou somar um intervalo a uma data, ou determinar se uma data está
  entre duas outras.

## Nível avançado

### Otimização 
Uma query lenta pode ser o gargalo da sua aplicação inteira.
Para otimizar queries, precisamos entender por que elas ficam lentas, e para isso 
precisamos saber o que o banco está fazendo.

O que você precisa aprender nesta fase:
- Gerar planos de execução e estatísticas de execução com `EXPLAIN` e `EXPLAIN ANALYZE`
- Aprender a ler os planos de execução e identificar gargalos usando eles
- Aprender a resolver os gargalos encontrados refatorando queries e adicionando índices onde necessário
- Recomendo terminar de ler o [Use the Index, Luke!](https://use-the-index-luke.com/)

### Window Functions
Funções de janela servem para fazer um cálculo sobre várias linhas escolhidas a partir de uma linha inicial.
Por exemplo: Para cada funcionário de uma empresa, você pode querer saber se o salário dele é maior que o
salário médio dos funcionários do mesmo departamento.
Com uma função de janela, isso pode ser feito em uma única query.

O que você precisa aprender nesta fase:
- Quais são as funções de janela suportadas pelo seu banco
- Criar análises complexas usando funções de janela

### PL/SQL
É possível criar suas próprias funções ou triggers (operações que são disparadas quando ocorre algum evento
específico) usando a extensão PL/SQL, uma linguagem procedural executada pelo próprio banco. Vale a pena
aprender um pouco de PL/SQL para implementar funcionalidades avançadas.

O que você precisa aprender nessa fase:
- Escrever funções que manipulam o banco usando PL/SQL
- Criar triggers para que o banco se atualize sozinho em resposta a certos eventos

### Administração de banco de dados
Para configurar o banco de dados, você provavelmente precisou criar um usuário e dar certas permissões a ele.
Se você trabalha com DB numa empresa, provavelmente os usuários necessários foram criados para você. Mas agora
é a hora de aprender a gerenciar usuários, permissões, bancos de dados (um único servidor pode gerir vários bancos)
e configurações do banco.

Este tópico é diferente para cada banco. Consulte a documentação do seu banco para estudar este tópico.

### Extensões
Todos os bancos SQL implementam extensões. Por exemplo, vários bancos permitem que você defina funções em
linguagens de programação diferentes de PL/SQL. Consulte a documentação do seu banco e aprenda como as extensões dele
funcionam.

### Funcionamento interno do banco
Consulte a documentação do seu banco e estude como ele implementa features do SQL que já estudamos como transações,
índices, ACID e assim por diante. Isso terá implicações importantes para otimização avanácada de performance.
