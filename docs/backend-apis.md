# APIs e Web Services

A Estante Infinita nasce como resposta ao cenário em que o preço elevado dos livros se impõe como barreira ao acesso à leitura. A proposta visa democratizar o acesso ao conhecimento por meio de um marketplace digital que privilegia a compra de livros usados, a troca entre usuários e a doação, ampliando o ciclo de vida dos acervos e reduzindo custos. O público-alvo são jovens e adultos a partir de 18 anos, estudantes e leitores engajados em práticas de consumo consciente e sustentável, que veem na leitura não apenas lazer, mas também oportunidade de formação cultural e acadêmica.

Para apoiar essa iniciativa, foi desenvolvida uma API RESTful em Node.js com Prisma ORM, que atua como interface central entre o backend e os clientes web. Essa API organiza e expõe recursos fundamentais da aplicação, como usuários, livros, anúncios, comentários e avaliações, garantindo consistência nas operações CRUD e sustentando os fluxos principais da plataforma.


## Objetivos da API

Esta API foi desenvolvida no padrão RESTful, utilizando Node.js e Prisma ORM. 

E será responsável por fornecer uma interface centralizada para comunicação entre o backend e os clientes web apoiando a plataforma de compra, venda e troca de livros, fornecendo uma camada de serviços confiável e escalável. 

Seus principais objetivos são: 

- Publicar anúncios: possibilitar operações de compra, venda e troca de livros. 

- Permitir interação entre usuários por meio de comentários em anúncios. 

- Expor endpoints REST organizados em recursos (usuários, livros, anúncios, comentários, avaliações), garantindo consistência nas operações CRUD. 

## Modelagem da Aplicação

**Modelo do banco de dados** para armazenar e gerenciar os dados, utilizando postgreSQL:
![Modelo do banco de dados](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-2-pe6-t2-turma2_g5/blob/main/docs/img/supabase.jpg)

**Modelo Diagrama Entidade Relacionamento:**
![DER](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-2-pe6-t2-turma2_g5/blob/main/docs/img/DER.png)

**Modelo Relacional:**
![Modelo relacional](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-2-pe6-t2-turma2_g5/blob/main/docs/img/modelo%20relacional.png)

- Usuário: informações dos usuários do sistema (id, nome, email, senha, criadoEm, atualizadoEm).
- Anuncio: publicação de um livro para troca, venda ou doação (id, titulo, autor, genero, condicao, tipo, ativo, criadoEm, atualizadoEm, usuarioId). 
- Comentario: texto de um usário de um anúncio (id, texto, criadoEm, atualizadoEm, usuarioId, anuncioId).
- Avaliacao: informações acerca do usuário (id, avaliadoId, comentário, criadoEm, atualizadoEm, usuarioId, avaliadoId).  

## Tecnologias Utilizadas

O projeto contempla o desenvolvimento de: 

- Backend e API: Implementação em Node.js (com Prisma ORM) responsável pela lógica de negócios e pela comunicação com o banco de dados. 
- Banco de Dados: Uso do PostgreSQL hospedado no Supabase, armazenando informações de usuários, livros, anúncios, comentários e avaliações. 
- Frontend: Aplicação web desenvolvida em Angular (Angular CLI), oferecendo uma interface intuitiva para cadastro, autenticação, publicação e navegação de anúncios. 

## API Endpoints

### Serviço de Usuários 

| Método  | Endpoint        | Descrição |
|---------|----------------|-----------|
| **POST**    | `/api/auth/register` | Cadastrar um novo usuário.   |
| **POST**    | `/api/auth/login` | Autenticar um usuário.    |
| **GET**    | `/api/usuarios/{id}` | Obter informações de um perfil.  |
| **PUT**    | `/api/usuarios/{id}` | Atualizar informações do perfil.  |
| **DELETE** | `/api/usuarios/{id}` | Deleta um usuário. |

:arrow_right: Exemplo de Requisição e Resposta para POST /api/auth/login :
```json
{ 
  
  "email": "giulia@pucminas.br", 

  "senha": "123@senha", 

} 
```  
Resposta: 200 OK
```json
{ 
  
  "token": "eyJhbGciOi...",

} 
```  


### Serviço de Anúncios 

| Método  | Endpoint        | Descrição |
|---------|----------------|-----------|
| **POST**    | `/api/anuncios` | Cria anúncio criando um livro junto.   |
| **GET**    | `/api/anuncios/{id}` | Detalha anúncio.   |
| **PUT**    | `/api/anuncios/{id}` | Atualiza anúncio.  |
| **DELETE** | `/api/anuncios/{id}` | Deleta um anúncio. |

:arrow_right: Exemplo de Requisição e Resposta para POST /api/anuncios :
```json
{ 

  "titulo": "O Mundo de Sofia", 

  "autor": "Jostein Gaarder", 

  "genero": "ROMANCE",

  "condicao": "NOVO",

  "tipo": "VENDA",

  "descricao": "Perfeito estado",

  "isbn": "9780374266424",

  "editora": "Companhia das Letras",

  "ano": "1995",

  "preço": "50.50"

} 
```  
Resposta: 201 Created 
```json
{ 

    "id": "6", 

    "titulo": "O Mundo de Sofia", 

    "autor": " Jostein Gaarder",

    "descricao": "Perfeito estado",

    "isbn": "9780374266424",

    "editora": "Companhia das Letras",

    "ano": "1995",

    "genero": " Romance",

    "preço": "50.50"

    "condicao": "Pequenas ranhuras",

    "tipo": "VENDA",

    "ativo": "true",

    "criadoEm": "2025-09-12T11:22:33.000Z", 

    "atualizadoEm": "2025-09-12T11:22:33.000Z"

    "usuarioId": 6

  } 
```

### Serviço de Comentário 

| Método  | Endpoint        | Descrição |
|---------|----------------|-----------|
| **POST**    | `/api/comentarios` | Cria comentário em um anúncio.   |
| **GET** | `/api/comentarios/{id}` | Detalha comentário em um anúncio. |
| **GET** | `/api/comentarios/anuncio/{anuncioId}` | Lista comentários de um anúncio. |
| **PUT** | `/api/comentarios/{id}` | Atualiza comentário (apenas autor). |
| **DELETE** | `/api/comentarios/{id}` | Deleta comentário em um anúncio (apenas autor). |

:arrow_right: Exemplo de Requisição e Resposta para PUT /api/comentarios/{id} :
```json
{ 

  "texto": "Podemos estar negociando o preço ?", 

} 
```  
Resposta: 200 OK
```json
{ 

    "id": 1, 

    "texto": "Podemos estar negociando o preço ?", 

    "createdEm": "2025-10-12T11:22:33.000Z", 

    "atualizadoEm": "2025-10-05T02:37:40.348Z"

    "usuarioId": 6, 
    
    "anuncioId": 4

  } 
```

### Serviço de Avalição 

| Método  | Endpoint        | Descrição |
|---------|----------------|-----------|
| **POST**    | `/api/avaliacoes` | Cria avaliação.   |
| **GET**    | `/api/avaliacoes/{id}` | Obtem avaliação.    |
| **GET**    | `/api/avaliacoes/anuncio/{anuncioId}` | Lista avaliações de um anúncio    |
| **PUT**    | `/api/avaliacoes/{id}` | Atualiza avaliação.    |
| **DELETE** | `/api/avaliacoes/{id}` | Deleta avaliação. |

:arrow_right: Exemplo de Requisição e Resposta para POST /api/avaliacoes :
```json
{ 

  "avaliacao": "REGULAR", 
  "anuncioId": 6

} 
```  
Resposta: 201 Created
```json
{ 

    "id": 4, 

    "texto": "REGULAR",

    "comentario": "null", 

    "createdEm": "2025-10-12T11:22:33.000Z", 

    "atualizadoEm": "2025-10-05T02:37:40.348Z"

    "usuarioId": 6, 
    
    "anuncioId": 6

  } 
```

## Considerações de Segurança

A única medida de segurança implementada será de garantir que todas as informações de autenticação do usuário, como senhas, serão armazenadas no banco de dados de forma criptografada. Não haverá, neste momento, controles adicionais de autorização granular, proteção contra ataques ou hardening de infraestrutura. 

## Implantação

A Vercel é responsável pela hospedagem e execução das funções serverless que compõem a API da aplicação. Conjuntamente, o Supabase provê o serviço de PostgreSQL gerenciado, atuando como a fonte de dados persistente. Por fim, o Prisma ORM gerencia a conexão e tradução das consultas entre o código da aplicação (Vercel) e o banco de dados (Supabase). 

**Software** 
- Node.js (LTS ≥ 20.x) como runtime do backend. 
- npm para gerenciamento de dependências. 
- Prisma CLI  
- PostgreSQL provido pelo Supabase como banco de dados relacional. 

**Hardware**
- Como a Vercel é serverless, os recursos são alocados por execução, mas a configuração alvo é equivalente a: 
- CPU: 1 vCPU por execução. 
- Memória: 512 MB por função. 
- Armazenamento: 4 GB  
- Rede: HTTPS/TLS habilitado por padrão (domínio da Vercel). 

**Aplicação:** Vercel  

**Banco de Dados:** Supabase (PostgreSQL) hospedado na mesma região para reduzir latência. 


## Testes
Os testes funcionais realizados são cruciais porque validam se a API cumpre o que promete ao usuário. Reduzindo risco de regressões e servem como evidência de qualidade, dessa forma, seguem os testes realizados:

 1. Objetivo: garantir unicidade de e-mail.
![teste](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-2-pe6-t2-turma2_g5/blob/main/docs/img/Testes%20Rafa/1-registro-de-usuario-falha-email-em-uso.png)

 2. Objetivo: permitir cadastro válido.
![teste](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-2-pe6-t2-turma2_g5/blob/main/docs/img/Testes%20Rafa/2-registro-de-usuario-sucesso.png)

 3. Objetivo: autenticar credenciais corretas.
![teste](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-2-pe6-t2-turma2_g5/blob/main/docs/img/Testes%20Rafa/3-login-usuario-sucesso.png)

 4. Objetivo: negar login com e-mail/senha inválidos.
![teste](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-2-pe6-t2-turma2_g5/blob/main/docs/img/Testes%20Rafa/4-login-usuario-falha-credenciais.png)

 5. Objetivo: retornar listagem dos anúncios.
![teste](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-2-pe6-t2-turma2_g5/blob/main/docs/img/Testes%20Rafa/5-listar-anuncios.png)

 6. Objetivo: retornar detalhes de um anúncio existente.
![teste](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-2-pe6-t2-turma2_g5/blob/main/docs/img/Testes%20Rafa/6-listar-um-anuncio.png)

 7. Objetivo: proteger rota de atualização por autenticação.
![teste](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-2-pe6-t2-turma2_g5/blob/main/docs/img/Testes%20Rafa/8-atualizar-anuncio-falha-token.png)

 8. Objetivo: proteger rota de atualização por autenticação.
![teste](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-2-pe6-t2-turma2_g5/blob/main/docs/img/Testes%20Rafa/8-atualizar-anuncio-falha-token.png)

 9. Objetivo: autorizar somente se for o dono na atualização.
![teste](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-2-pe6-t2-turma2_g5/blob/main/docs/img/Testes%20Rafa/9-atualizar-anuncio-falha-usuario.png)

 10. Objetivo: atualizar anúncio do dono autenticado.
![teste](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-2-pe6-t2-turma2_g5/blob/main/docs/img/Testes%20Rafa/10-atualizar-anuncio-sucesso.png)

 11. Objetivo: criar anúncio.
![teste](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-2-pe6-t2-turma2_g5/blob/main/docs/img/Testes%20Rafa/11-criar-anuncio-sucesso.png)

 12. Objetivo: criar avaliação para um anúncio.
![teste](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-2-pe6-t2-turma2_g5/blob/main/docs/img/Testes%20Rafa/12-criar-avaliacao-sucesso.png)

 13. Objetivo: impedir o mesmo usuário de dar nota no mesmo anúncio duas vez
![teste](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-2-pe6-t2-turma2_g5/blob/main/docs/img/Testes%20Rafa/13-criar-avaliacao-falha-usuario.png)

 14. Objetivo: permitir atualizar a própria avaliação
![teste](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-2-pe6-t2-turma2_g5/blob/main/docs/img/Testes%20Rafa/14-atualizar-avaliacao-sucesso.png)

 15. Objetivo: retornar erro quando a avaliação não existe.
![teste](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-2-pe6-t2-turma2_g5/blob/main/docs/img/Testes%20Rafa/15-atualizar-avaliacao-falha-inexistente.png)

 16. Objetivo: criar comentário vinculado a um anúncio.
![teste](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-2-pe6-t2-turma2_g5/blob/main/docs/img/Testes%20Rafa/16-criar-comentario-sucesso.png)

 17. Objetivo: permitir que o autor edite seu comentário.
![teste](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-2-pe6-t2-turma2_g5/blob/main/docs/img/Testes%20Rafa/17-atualizar-comentario-sucesso.png)

 18. Objetivo: restringir edição a quem criou o comentário.
![teste](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-2-pe6-t2-turma2_g5/blob/main/docs/img/Testes%20Rafa/18-atualizar-comentario-falha-usuario.png)

 19. Objetivo: listar comentários de um anúncio específico.
![teste](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-2-pe6-t2-turma2_g5/blob/main/docs/img/Testes%20Rafa/19-listar-comentarios-por-anuncio-sucesso.png)

 20. Objetivo: listar avaliações de um anúncio
![teste](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2025-2-pe6-t2-turma2_g5/blob/main/docs/img/Testes%20Rafa/20-listar-avaliacoes-por-anuncio-sucesso.png)


# Referências

Verce: https://vercel.com/docs

Supabase: https://supabase.com/docs

PostgreSQL: https://www.postgresql.org/docs/

Prisma ORM: https://www.prisma.io/docs

Node.js: https://nodejs.org/docs/latest/api/

TypeScript: https://www.typescriptlang.org/pt/docs/


# Planejamento

##  Quadro de tarefas

> Apresente a divisão de tarefas entre os membros do grupo e o acompanhamento da execução, conforme o exemplo abaixo.

### Semana 1

Atualizado em: 21/04/2024

| Responsável   | Tarefa/Requisito | Iniciado em    | Prazo      | Status | Terminado em    |
| :----         |    :----         |      :----:    | :----:     | :----: | :----:          |
| Todos        | Correção da Etapa 1 | 01/09/2025     | 07/09/2025 | ✔️    | 07/09/2025      |
| Isadora/Jaime/Rafael | Planejar APIs e Web Services BackEnd | 08/09/2025      | 14/09/2025 | ✔️     | 14/09/2025   |
| Romulo       | Planejar APIs e Web Services FrontEnd | 08/09/2025   | 14/09/2025  | ✔️    |  14/09/2025   |
| Isadora/Jaime/Rafael | Executar APIs e Web Services BackEnd  | 15/09/2025        | 30/09/2025 | ✔️    |  30/09/2025   |
| Romulo   | Executar APIs e Web Services FrontEnd  | 15/09/2025        | 30/09/2025 | ✔️    |  30/09/2025    |
| Rafael   | Testes APIs e Web Services  | 01/10/2025        | 01/10/2025 | ✔️    |  04/10/2025    |
| Giulia   | Gerenciar e documentar serviços de TI  | 08/09/2025        |  05/10/2025 | ✔️    |  05/10/2025    |

Legenda:
- ✔️: terminado
- 📝: em execução
- ⌛: atrasado
- ❌: não iniciado

