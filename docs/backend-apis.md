# APIs e Web Services

~O planejamento de uma aplicação de APIS Web é uma etapa fundamental para o sucesso do projeto. Ao planejar adequadamente, você pode evitar muitos problemas e garantir que a sua API seja segura, escalável e eficiente.~
~Aqui estão algumas etapas importantes que devem ser consideradas no planejamento de uma aplicação de APIS Web.~
~[Inclua uma breve descrição do projeto.]~

A Estante Infinita nasce como resposta ao cenário em que o preço elevado dos livros se impõe como barreira ao acesso à leitura, especialmente após os recentes aumentos registrados em gêneros como Ficção. A proposta justifica-se pela necessidade de democratizar o acesso ao conhecimento, criando um marketplace digital que privilegia a compra de usados e a doação gratuita, ampliando o ciclo de vida dos acervos e reduzindo custos. O público-alvo são jovens e adultos a partir de 18 anos, estudantes e leitores engajados em práticas de consumo consciente e sustentável, que buscam alternativas econômicas para acessar novos títulos e veem na leitura não apenas lazer, mas também oportunidade de formação cultural e acadêmica.


## Objetivos da API

~O primeiro passo é definir os objetivos da sua API. O que você espera alcançar com ela? Você quer que ela seja usada por clientes externos ou apenas por aplicações internas? Quais são os recursos que a API deve fornecer?~
~[Inclua os objetivos da sua api.]~

Esta API foi desenvolvida no padrão RESTful, utilizando Node.js e Prisma ORM. 

E será responsável por fornecer uma interface centralizada para comunicação entre o backend e os clientes web apoiando a plataforma de compra, venda e troca de livros, fornecendo uma camada de serviços confiável e escalável. 

Seus principais objetivos são: 

- Publicar anúncios: possibilitar operações de compra, venda e troca de livros. 

- Permitir interação entre usuários por meio de comentários em anúncios. 

- Expor endpoints REST organizados em recursos (usuários, livros, anúncios, comentários, avaliações), garantindo consistência nas operações CRUD. 

## Modelagem da Aplicação
~[Descreva a modelagem da aplicação, incluindo a estrutura de dados, diagramas de classes ou entidades, e outras representações visuais relevantes.]~

Segue um modelo relacional para armazenar e gerenciar os dados, utilizando postgreSQL como banco de dados. 
![Diagrama](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-2-pe6-t2-turma2_g5/blob/main/docs/img/Imagem%20do%20WhatsApp%20de%202025-10-01%20%C3%A0(s)%2018.06.33_850fed5c.jpg)

Usuário: informações dos usuários do sistema (id, nome, email, senha, criadoEm, atualizadoEm).

Anuncio: publicação de um livro para troca, venda ou doação (id, titulo, autor, descricao, isbn, editora, ano, genero, preco, condicao, tipo, ativo, criadoEm, atualizadoEm, usuarioId). 

Comentario: texto de um usário de um anúncio (id, texto, criadoEm, atualizadoEm, usuarioId, anuncioId).

Avaliacao: informações acerca do usuário (id, avaliação, comentário, criadoEm, atualizadoEm, usuarioId, avaliadoId).  

## Tecnologias Utilizadas

~Existem muitas tecnologias diferentes que podem ser usadas para desenvolver APIs Web. A tecnologia certa para o seu projeto dependerá dos seus objetivos, dos seus clientes e dos recursos que a API deve fornecer.~
~[Lista das tecnologias principais que serão utilizadas no projeto.]~

O projeto contempla o desenvolvimento de: 

Backend e API: Implementação em Node.js (com Prisma ORM) responsável pela lógica de negócios e pela comunicação com o banco de dados. 

Banco de Dados: Uso do PostgreSQL hospedado no Supabase, armazenando informações de usuários, livros, anúncios, comentários e avaliações. 

Frontend: Aplicação web desenvolvida em Angular (Angular CLI), oferecendo uma interface intuitiva para cadastro, autenticação, publicação e navegação de anúncios. 

## API Endpoints

### Serviço de Usuários 

| Método  | Endpoint        | Descrição |
|---------|----------------|-----------|
| **POST**    | `/api/auth/register` | Cadastrar um novo usuário.   |
| **POST**    | `/api/auth/login` | Autenticar um usuário.    |
| **GET**    | `/api/usuarios/{id}` | Obter informações de um perfil.  |
| **PUT**    | `/api/usuarios/{id}` | Atualizar informações do perfil.  |
| **DELETE** | `/api/usuarios/{id}` | Deleta um usuário. |

### Serviço de Anúncios 

| Método  | Endpoint        | Descrição |
|---------|----------------|-----------|
| **POST**    | `/api/anuncios` | Cria anúncio criando um livro junto.   |
| **GET**    | `/api/anuncios/{id}` | Detalha anúncio (inclui livro e, opcionalmente, comentários paginados).    |
| **PUT**    | `/api/anuncios/{id}` | Atualiza anúncio.  |
| **DELETE** | `/api/anuncios/{id}` | Deleta um anúncio. |

### Serviço de Comentário 

| Método  | Endpoint        | Descrição |
|---------|----------------|-----------|
| **POST**    | `/api/comentarios` | Cria comentário em um anúncio.   |
| **DELETE** | `/api/comentarios/{id}` | Deleta comentário em um anúncio. |

### Serviço de Comentário 

| Método  | Endpoint        | Descrição |
|---------|----------------|-----------|
| **POST**    | `/api/avaliacoes` | Cria anúncio criando um livro junto.   |
| **PUT**    | `/api/avaliacoes/{id}` | Atualiza avaliação.    |
| **DELETE** | `/api/avaliacoes/{id}` | Deleta avaliação. |
 

### Exemplos de requisições e respostas: 

Para: cadastrar um livro. 
```json
{ 

  "titulo": "O Mundo de Sofia", 

  "autor": " Jostein Gaarder", 

  "descricao": "Pequenas ranhuras", 

} 
```  
Resposta: 201 OK 
```json
{ 

  "success": true, 

  "data": { 

    "id": "a0f9d6a2-4a0a-4a3e-8af9-2a1b9f1c9f00", 

    "titulo": "O Mundo de Sofia", 

    "autor": " Jostein Gaarder", 

    "descricao": "Pequenas ranhuras", 

    "createdAt": "2025-09-12T11:22:33.000Z", 

    "updatedAt": "2025-09-12T11:22:33.000Z" 

  } 

} 
```

Para: Obter informações de um perfil. 
```json
{ 

  "success": true, 

  "data": { 

    "id": "7b3f8b7f-0e8a-4b07-9e05-1e1d9b7b6b10", 

    "name": "Giulia Fernandes", 

    "email": "giulia@pucminas.br", 

    "createdAt": "2025-09-01T12:34:56.000Z", 

    "updatedAt": "2025-09-10T08:20:30.000Z" 

  } 

} 
```

## Considerações de Segurança
~[Discuta as considerações de segurança relevantes para a aplicação distribuída, como autenticação, autorização, proteção contra ataques, etc.]~

A única medida de segurança implementada será de garantir que todas as informações de autenticação do usuário, como senhas, serão armazenadas no banco de dados de forma criptografada. Não haverá, neste momento, controles adicionais de autorização granular, proteção contra ataques ou hardening de infraestrutura. 

## Implantação

~[Instruções para implantar a aplicação distribuída em um ambiente de produção.]~

A Vercel é responsável pela hospedagem e execução das funções serverless que compõem a API da aplicação. Conjuntamente, o Supabase provê o serviço de PostgreSQL gerenciado, atuando como a fonte de dados persistente. Por fim, o Prisma ORM gerencia a conexão e tradução das consultas entre o código da aplicação (Vercel) e o banco de dados (Supabase). 

Software 
- Node.js (LTS ≥ 20.x) como runtime do backend. 
- npm para gerenciamento de dependências. 
- Prisma CLI  
- PostgreSQL provido pelo Supabase como banco de dados relacional. 

Hardware 
- Como a Vercel é serverless, os recursos são alocados por execução, mas a configuração alvo é equivalente a: 
- CPU: 1 vCPU por execução. 
- Memória: 512 MB por função. 
- Armazenamento: 2 GB  
- Rede: HTTPS/TLS habilitado por padrão (domínio da Vercel). 

Aplicação: Vercel  

Banco de Dados: Supabase (PostgreSQL) hospedado na mesma região para reduzir latência. 


## Testes

[Descreva a estratégia de teste, incluindo os tipos de teste a serem realizados (unitários, integração, carga, etc.) e as ferramentas a serem utilizadas.]

1. Crie casos de teste para cobrir todos os requisitos funcionais e não funcionais da aplicação.
2. Implemente testes unitários para testar unidades individuais de código, como funções e classes.
3. Realize testes de integração para verificar a interação correta entre os componentes da aplicação.
4. Execute testes de carga para avaliar o desempenho da aplicação sob carga significativa.
5. Utilize ferramentas de teste adequadas, como frameworks de teste e ferramentas de automação de teste, para agilizar o processo de teste.

# Referências

Inclua todas as referências (livros, artigos, sites, etc) utilizados no desenvolvimento do trabalho.

# Planejamento

##  Quadro de tarefas

> Apresente a divisão de tarefas entre os membros do grupo e o acompanhamento da execução, conforme o exemplo abaixo.

### Semana 1

Atualizado em: 21/04/2024

| Responsável   | Tarefa/Requisito | Iniciado em    | Prazo      | Status | Terminado em    |
| :----         |    :----         |      :----:    | :----:     | :----: | :----:          |
| AlunaX        | Introdução | 01/02/2024     | 07/02/2024 | ✔️    | 05/02/2024      |
| AlunaZ        | Objetivos    | 03/02/2024     | 10/02/2024 | 📝    |                 |
| AlunoY        | Histórias de usuário  | 01/01/2024     | 07/01/2005 | ⌛     |                 |
| AlunoK        | Personas 1  |    01/01/2024        | 12/02/2005 | ❌    |       |

#### Semana 2

Atualizado em: 21/04/2024

| Responsável   | Tarefa/Requisito | Iniciado em    | Prazo      | Status | Terminado em    |
| :----         |    :----         |      :----:    | :----:     | :----: | :----:          |
| AlunaX        | Página inicial   | 01/02/2024     | 07/03/2024 | ✔️    | 05/02/2024      |
| AlunaZ        | CSS unificado    | 03/02/2024     | 10/03/2024 | 📝    |                 |
| AlunoY        | Página de login  | 01/02/2024     | 07/03/2024 | ⌛     |                 |
| AlunoK        | Script de login  |  01/01/2024    | 12/03/2024 | ❌    |       |

Legenda:
- ✔️: terminado
- 📝: em execução
- ⌛: atrasado
- ❌: não iniciado

