<img width="1897" height="925" alt="Captura de tela 2025-11-03 145119" src="https://github.com/user-attachments/assets/38faee97-53f8-4d25-b431-b1946719d11a" /># Front-end Web

Esta é a interface principal da Estante Infinita, desenvolvida em Angular com suporte a SSR (Angular Universal) para otimização de desempenho e SEO. O front-end é responsável por proporcionar uma experiência fluida e responsiva aos usuários, permitindo navegação simples, autenticação segura e interação direta com os anúncios.

O objetivo deste front-end é oferecer uma plataforma completa para criação, gerenciamento e visualização de anúncios, possibilitando que cada usuário publique seus próprios itens, interaja com outros por meio de comentários e manifeste interesse nos anúncios disponíveis.

Objetivos específicos do Front-end:
- Gerenciamento de anúncios (CRUD): permitir criar, editar, listar e visualizar anúncios de forma intuitiva e eficiente.
- Interação e engajamento: possibilitar que usuários adicionem comentários em cada anúncio, demonstrando interesse e promovendo troca entre os participantes.
- Componentização e reuso: utilizar componentes reutilizáveis, como cabeçalho e rodapé, para garantir consistência visual e manutenção simplificada.
- SEO e performance: aplicar SSR (Server-Side Rendering) para melhorar a indexação nos mecanismos de busca e otimizar o tempo de carregamento.

Stack utilizada:
- Framework: Angular
- Linguagem: TypeScript

Como executar (modo de desenvolvimento):
<br>Execute npm install para instalar as dependências e, em seguida, ng serve para iniciar o servidor local.

## Projeto da Interface Web

A interface web foi desenvolvida com o framework Angular, utilizando TypeScript e suporte a SSR (Angular Universal).
<br>O design segue uma estética minimalista e responsiva, com predominância de tons branco, preto e magenta, transmitindo uma experiência acolhedora, organizada e intuitiva.
<br>O layout segue uma estrutura com cabeçalho fixo, menu lateral e área principal de conteúdo.
- Home: página inicial que apresenta uma saudação de boas-vindas (“Bem-vindo à Estante Infinita”) e permite ao usuário descobrir os anúncios dos livros, incluindo incluindo uma barra de pesquisa e um menu para gêneros. 

- Login e Registro: telas de autenticação implementadas com formulários reativos (Reactive Forms), garantindo validação de campos e envio de dados à API de autenticação via JWT. O login realiza a verificação das credenciais e, em caso de sucesso, armazena o token JWT e as informações do usuário no sessionStorage, permitindo o acesso às áreas restritas da aplicação. Já o registro possibilita criar uma nova conta informando nome, e-mail e senha, apresentando feedback visual e opção para redirecionar o usuário à página de login.

- Book Page (Detalhes do Anúncio): exibe as informações completas de cada livro, incluindo descrição, autor, gênero e espaço para comentários, onde os usuários podem demonstrar interesse no anúncio.

- Profile Page: painel onde o usuário autenticado pode gerenciar seus próprios anúncios, editar ou excluir seu anúncio e visualizar interações recebidas.

### Wireframes
Página Home:
<p align="center"> <img width="617" height="769" alt="image" src="https://github.com/user-attachments/assets/adcd3e89-a426-4ef9-ba9e-0d5481a085f4" />

Página Página de Detalhes do Livro:
<p align="center"> <img width="618" height="625" alt="image" src="https://github.com/user-attachments/assets/20bcfb94-5b52-48b3-b279-78aacb8fc7d1" />

Página do Perfil do Usuário:
<p align="center"> <img width="615" height="386" alt="image" src="https://github.com/user-attachments/assets/dec52594-cac6-4cf2-9610-8337da2b3e42" />


### Design Visual

Minimalista, moderno e limpo. O design prioriza a legibilidade e a organização, utilizando um layout estruturado e um uso generoso de espaço em branco para evitar poluição visual.

Paleta de Cores:
A paleta é primariamente neutra, com um único e forte ponto de cor para destaque e identidade.
Branco e Cinza Claro: O fundo principal da área de conteúdo é branco, enquanto o "hero banner" (a faixa superior) usa um tom de cinza muito claro. Isso cria uma base suave e limpa.
Preto e Cinza Escuro: Usados para a maior parte da tipografia (títulos, textos, nomes de autores) e para os ícones. Garantem alto contraste e excelente legibilidade.
Vinho/Magenta: Esta é a cor de destaque principal. É usada em elementos de ação ou ênfase, como o subtítulo ("Descubra, leia...") e as etiquetas (tags) de categoria abaixo de cada livro (ex: "FICÇÃO CIENTÍFICA", "FANTASIA").

Tipografia:
A tipografia é inteiramente sans-serif (sem serifa), o que contribui para a sensação de modernidade e clareza.
Hierarquia: Há uma hierarquia visual clara. Títulos principais (como "Bem-vindo à Estante Infinita" e os títulos dos livros, ex: "Duna") usam um peso bold (negrito) e um tamanho de fonte maior.
Texto de Apoio: O subtítulo e as descrições dos livros usam um peso de fonte mais leve (regular ou light) e um tamanho menor, facilitando a diferenciação entre título e conteúdo.
Caixa Alta (Uppercase): O logo no canto superior esquerdo ("ESTANTE INFINITA") e o texto nas etiquetas de categoria (ex: "AUTOBIOGRAFIA") estão em caixa alta, dando-lhes um aspecto de rótulo e destacando-os.

Ícones e Elementos Gráficos:
Os ícones e elementos gráficos são simples e consistentes, reforçando o minimalismo.Ícones de Categoria: A fileira de ícones de gênero (Regiões, Poesia, Fantasia, etc.) utiliza um estilo "line-art" (apenas contorno). São monocromáticos (pretos), simples e fáceis de reconhecer.Ícones de UI: Ícones de interface padrão, como o ícone de busca (lupa) na barra de pesquisa e o menu "hambúrguer" (três linhas) no canto superior direito, seguem o mesmo estilo de contorno e simplicidade. Esta é uma escolha de design inteligente que conecta o conteúdo diretamente ao nome da marca ("Estante Infinita").

Layout e Outros Elementos:
Layout em Grade (Grid): O conteúdo principal, especialmente a lista de livros, é organizado em um sistema de grade (cards). Isso cria uma sensação de ordem, alinhamento e facilita a varredura visual.
Espaço em Branco: O uso de espaço em branco (ou espaço negativo) é fundamental neste design. Ele separa claramente a seção de categorias, a barra de pesquisa e a lista de livros, permitindo que cada elemento "respire".
Cards de Livro: Cada livro é apresentado em um "card" individual. Este card contém a imagem, título, autor, uma breve descrição e a etiqueta de categoria colorida.
Barra de Pesquisa: É um elemento simples, com cantos arredondados e um ícone claro, integrando-se de forma suave ao restante do layout.

<img width="1900" height="751" alt="image" src="https://github.com/user-attachments/assets/79c97fb0-5223-46dd-8b82-b153ef48effc" />

<img width="1832" height="767" alt="image" src="https://github.com/user-attachments/assets/1dcdd455-8623-4eee-9999-7ab005285e3e" />

<img width="1863" height="811" alt="image" src="https://github.com/user-attachments/assets/512a9b38-caa0-412d-a435-f8a4048b5300" />


## Fluxo de Dados

flowchart LR
    subgraph UI["🖥️ Interface do Usuário (Angular)"]
        A[Login Component]
        B[Home]
        C[BookPage]
        D[Create/Edit Anúncio]
        E[Profile]
    end

    subgraph Services["📦 Services (Angular)"]
        S1[SiteService]
        S2[AnuncioService]
        S3[ComentarioService]
        S4[AvaliacaoService]
    end

    subgraph Auth["🔐 AuthInterceptor"]
        I[Verifica token e adiciona Authorization Header]
    end

    subgraph Backend["⚙️ Backend (Node.js + Express)"]
        BE1[/AuthController/]
        BE2[/AnuncioController/]
        BE3[/ComentarioController/]
        BE4[/AvaliacaoController/]
        DB[(Banco de Dados via Prisma)]
    end

    subgraph SSR["🌐 Angular Universal (Server-side Rendering)"]
        SSR1[server.ts]
        SSR2[main.server.ts]
    end

    %% Fluxo principal
    UI --> Services
    Services --> I
    I --> Backend
    Backend --> DB
    Backend --> Services
    Services --> UI

    %% Login
    A -->|signIn()| S1 -->|POST /auth/login| BE1 --> DB
    BE1 -->|{user, token}| UI
    UI -->|sessionStorage| I

    %% SSR
    SSR1 --> SSR2 --> UI


## Tecnologias Utilizadas
Angular (framework) — aplicação SPA e componentes.

TypeScript — linguagem principal.

Angular Router — navegação e rotas da aplicação.

SCSS — pré-processador de estilos.

HTML5 — marcação e estilos.

Node.js + npm — execução local, scripts e build.

Prisma ORM — gerenciamento de dados.

Express (ou servidor Node) — arquivo server.ts indica servidor para SSR.

REST APIs / JSON — comunicação com backend (via serviços e interceptors).

JWT (autenticação) — usado com auth.interceptor para chamadas autenticadas.

Git — controle de versão.


## Considerações de Segurança

Esta aplicação utiliza Angular (Frontend), Angular Universal + Express (SSR) e REST APIs protegidas por JWT. Por se tratar de uma arquitetura distribuída, é necessário considerar cuidadosamente aspectos como autenticação, autorização, armazenamento seguro de tokens, injeção de conteúdo e proteção do servidor SSR.

⚠️ 1. Principais Riscos de Segurança
Risco	Descrição
Exfiltração de Token (XSS)	O JWT é armazenado em sessionStorage. Caso ocorra XSS, o token pode ser roubado e reutilizado.
CSRF (Cross-Site Request Forgery)	Se tokens forem migrados para cookies sem proteção adequada (SameSite/CSRF-Token), o backend pode processar ações não autorizadas.
CSP Fraca (Content Security Policy)	A configuração atual permite 'unsafe-inline' e 'unsafe-eval', facilitando execução de scripts maliciosos.
SSR sem autenticação segura	O código executado via server-side rendering não tem acesso a sessionStorage, podendo gerar falhas de autenticação ou vazamento de informações.
Brute Force / Enumeração de Usuario	Falta de rate limiting nas rotas de autenticação.
Uploads/Inputs sem validação	Pode permitir injeção de comandos, scripts, arquivos maliciosos ou corrompidos.
Headers de segurança ausentes	Ausência de HSTS, X-Frame-Options, X-Content-Type-Options, Referrer-Policy, entre outros.
Dependências desatualizadas	Pacotes sem atualização podem conter vulnerabilidades conhecidas (CVEs).
✅ 2. Recomendações de Alta Prioridade
Ação	Objetivo
1. Armazenamento Seguro de Tokens	Migrar de sessionStorage/localStorage para cookies httpOnly + Secure + SameSite=strict.
2. Access Token curto + Refresh Token	Access tokens de 5–15 min e refresh tokens rotacionáveis via /auth/refresh.
3. Helmet + Rate Limit no Express	Ativar headers de segurança automaticamente e limitar tentativas de login.
4. CSP Segura	Remover 'unsafe-inline'/'unsafe-eval' e adotar CSP restrita com nonces ou hashes.
5. CORS Restritivo	Permitir apenas domínios específicos da aplicação.
6. HTTPS Obrigatório + HSTS	Redirecionamento automático para HTTPS e uso de Strict-Transport-Security.
7. Validação de Inputs no Backend	Usar bibliotecas como class-validator, Joi ou Zod.
8. SSR Seguro	No SSR, ler o token de cookies httpOnly (não de sessionStorage) e enviá-lo manualmente nas requisições.
🛠️ 3. Trecho de Configuração Express (Produção)
import express from "express";
import helmet from "helmet";
import rateLimit from "express-rate-limit";
import cors from "cors";

const app = express();

// Segurança de headers
app.use(helmet());

// CORS restrito
app.use(cors({
  origin: "http://localhost:4200",
  credentials: true,
}));

// Rate limiting para autenticação
app.use("/auth/login", rateLimit({
  windowMs: 15 * 60 * 1000,
  max: 5,
  message: "Muitas tentativas de login. Tente novamente mais tarde."
}));

// HTTPS obrigatório (se usando proxy/nginx)
app.enable("trust proxy");
app.use((req, res, next) => {
  if (req.secure) return next();
  res.redirect("https://" + req.headers.host + req.url);
});

🌐 4. Proteções no Frontend (Angular)

✔ Usar Route Guards e controle de acesso baseado em papéis (RBAC).
✔ Evitar DomSanitizer.bypassSecurityTrust... sem necessidade.
✔ Não expor tokens no localStorage/sessionStorage.
✔ Atualizar dependências com npm audit e npm outdated.
✔ Logout automático ao expirar o token (token expiration handling).

🖥 5. Segurança no SSR (Angular Universal)
Problema	Solução
SSR não acessa sessionStorage/localStorage	Usar cookies httpOnly para enviar o token ao servidor.
Requisições feitas no SSR sem autenticação	Ler o cookie do request e injetar manualmente o bearer token nas requisições do SSR.
Vazamento de dados no HTML renderizado	Não injetar dados sensíveis diretamente durante a renderização.

## Implantação

https://turma2-g5-e-commerce-frontend.onrender.com/

## Testes

### Estratégia de Testes da Aplicação (Baseada em RF e RNF)

A estratégia de teste tem como objetivo garantir que o sistema atenda plenamente aos requisitos funcionais e não funcionais, entregando uma aplicação confiável, segura, responsiva, intuitiva e com bom desempenho. Serão realizados testes unitários, integração, funcionais, interface, performance, segurança e carga, utilizando ferramentas adequadas para cada objetivo.

### 1. Testes dos Requisitos Funcionais (RF)

Para os requisitos funcionais RF-001 a RF-006, serão criados casos de teste garantindo cobertura completa das funcionalidades essenciais da aplicação.

### 2. Testes dos Requisitos Não Funcionais (RNF)

Serão testados os RNFs, para garantir que os mesmos não falham.

### 3. Testes Unitários

Cobrirão:

- Funções auxiliares

- Validação dos campos

- Lógicas de filtro e busca

Ferramentas:
- Jest

### 4. Testes de Integração

Cobrirão:

- Fluxo completo de CRUD

- Login + sessão + ações

- Associação correta entre comentários/avaliações e anúncios

- Rotas do Next.js App Router

- Comunicação com o banco de dados

Ferramentas:
- Jest + Supertest

### 5. Testes de Carga / Performance

Cobrirão:

- RNF-004 (busca ≤ 2s)

- RNF-005 (detalhes ≤ 3s)

- Stress test: 200, 300, 500 usuários simultâneos

Ferramentas:
- k6

### 6. Testes de Segurança

Cobrirão:

- RNF-006 (senhas criptografadas)

- Testes básicos de vulnerabilidade:

- SQL Injection

- XSS

### 7. Ferramentas
| Tipo de Teste     | Ferramentas                   |
| ----------------- | ----------------------------- |
| Unitário          | Jest                          |
| Integração        | Jest + Supertest              |
| Carga/Performance | k6                            |
| Responsividade    | Chrome DevTools               |

## MATRIZ DE RASTREABILIDADE — Requisitos x Casos de Teste

### 1. Requisitos Funcionais (RF)
| ID do Requisito | Descrição                                 | Casos de Teste Associados                                                                                                                                                                                                                                                                           |
| --------------- | ----------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **RF-001**      | Cadastro e login de usuários              | CT-001 Cadastro válido<br>CT-002 E-mail duplicado<br>CT-003 Login válido<br>CT-004 Login inválido<br>CT-005 Login usuário inexistente<br>CT-006 Logout<br>                                                                    |
| **RF-002**      | CRUD de anúncios (criar, editar, excluir) | CT-007 Criar anúncio válido<br>CT-008 Criar anúncio com campos faltando<br>CT-009 Editar anúncio válido<br>CT-010 Impedir edição por usuário não autorizado<br>CT-011 Excluir anúncio válido |
| **RF-003**      | Visualização de detalhes do anúncio       | CT-012 Exibir detalhes completo<br>CT-013 Anúncio inexistente<br>CT-014 Layout responsivo dos detalhes<br>CT-015 Carregamento dos dados                                                                                                                                                             |
| **RF-004**      | Busca e filtros por categoria             | CT-016 Busca por título<br>CT-017 Filtro por gênero<br>CT-018 Busca sem resultados<br>CT-019 Tempo da busca (ligado ao RNF-004)                                                                             |
| **RF-005**      | Aba de comentários                        | CT-020 Criar comentário válido<br>CT-021 Comentário inválido (vazio/limite)<br>CT-022 Listar comentários<br>CT-023 Excluir comentário (se permitido)<br>CT-024 Comportamento com muitos comentários                                                   |
| **RF-006**      | Avaliar anúncio                           | CT-025 Avaliação válida<br>CT-026 Visualização de avaliações                                                                                                                    |

## CASOS DE TESTE DETALHADOS 
### RF-001 — Cadastro e Login
#### CT-001 — Cadastro com dados válidos

- Objetivo: Validar o cadastro de um novo usuário.

- Pré-condição: E-mail não existe no sistema.

- Entradas: Nome, e-mail válido, senha válida.

- Passos:
  1. Acessar tela de cadastro.
  2. Preencher campos corretamente.
  3. Clicar em "Cadastrar".

- Resultado esperado:
  - API retorna 201
  - Conta criada
  
- Resultado obtido:
  - API retorna 201
  - Conta criada

<img width="1898" height="866" alt="Captura de tela 2025-11-02 214344" src="https://github.com/user-attachments/assets/a7e40278-f959-4d63-bac2-5b19b55a2ff1" />


#### CT-002 — Cadastro com e-mail duplicado

- Objetivo: Impedir duplicidade.

- Pré-condição: E-mail já cadastrado.

- Entradas: Nome, e-mail existente, senha válida.

- Resultado esperado:
  - Cadastro rejeitado
  - Mensagem de erro. Erro ao efetuar registro. Chame um administrador.

- Resultado obtido:
  - Cadastro rejeitado
  - Mensagem "Erro ao efetuar registro. Chame um administrador."
<img width="1884" height="912" alt="Captura de tela 2025-11-02 214538" src="https://github.com/user-attachments/assets/31a0f702-add7-4bb3-b99c-cf84f4ad4bdb" />

#### CT-003 — Login com credenciais válidas

- Objetivo: Confirmar autenticação.

- Entradas: E-mail e senha corretos.

- Resultado esperado:
  - Login efetuado
  - Token gerado
  - Redirecionamento

- Resultado obtido:
  - Login efetuado
  - Token gerado
  - Redirecionamento
<img width="1898" height="861" alt="Captura de tela 2025-11-02 214741" src="https://github.com/user-attachments/assets/ef6ad173-2047-407b-b62e-0f1b96a1d8c7" />

#### CT-004 — Login com senha incorreta

- Objetivo: Impedir acesso indevido.

- Entradas: E-mail válido + senha errada.

- Resultado esperado:
  - Acesso negado – 401
  - Mensagem de erro

- Resultado obtido:
  - Acesso negado – 401
  - Mensagem “Erro ao efetuar login. Chame um administrador.”
<img width="1897" height="911" alt="Captura de tela 2025-11-02 214828" src="https://github.com/user-attachments/assets/28f4ebd5-1915-423a-9a59-acee2446a5b4" />
  
#### CT-005 — Login com usuário inexistente

- Resultado esperado:
  - Erro 404 ou 401
  - Mensagem genérica.

- Resultado obtido:
  - Acesso negado – 401
  - Mensagem “Erro ao efetuar login. Chame um administrador.”
<img width="1894" height="912" alt="Captura de tela 2025-11-02 214936" src="https://github.com/user-attachments/assets/c70a6566-94c9-4248-9b0c-8a6d9e2bbd78" />

#### CT-006 — Logout

- Objetivo: Encerrar sessão.

- Resultado esperado:
  - Token removido
  - Redirecionamento para login.

- Resultado obtido:
  - Token removido
  - Redirecionamento para login.
<img width="1899" height="868" alt="Captura de tela 2025-11-02 215039" src="https://github.com/user-attachments/assets/460d14fd-bb28-45d0-b8c2-39cc46320b38" />

### RF-002 — CRUD de Anúncios
#### CT-007 — Criar anúncio com dados válidos

- Objetivo: Validar criação completa.

- Entradas: Título, autor, descrição, gênero, editora, ano, preço, condição, tipo.

- Resultado esperado:
  - Anúncio criado
  - Exibido na listagem
  - Feedback positivo

- Resultado obtido:
  - Anúncio criado
  - Exibido na listagem
  - Feedback positivo
   <img width="1892" height="963" alt="Captura de tela 2025-11-03 144944" src="https://github.com/user-attachments/assets/76eb65f1-99c3-47d6-90b7-5ca10de208da" />

#### CT-008 — Criar anúncio com campos faltando

- Resultado esperado:
  - Formulário bloqueia

- Resultado obtido:
  - Formulário bloqueia
<img width="1899" height="866" alt="Captura de tela 2025-11-02 222053" src="https://github.com/user-attachments/assets/e48226ef-e206-435b-8505-7efcfdc6ea87" />


#### CT-009 — Editar anúncio válido

- Objetivo: Validar atualização.

- Resultado esperado:
  - API retorna 200
  - Dados atualizados na tela

- Resultado obtido:
  - API retorna 200
  - Dados atualizados na tela
<img width="1899" height="812" alt="Captura de tela 2025-11-03 145044" src="https://github.com/user-attachments/assets/2d3dbcfd-2cab-46a4-afad-dee5fe5cf9cd" />

#### CT-010 — Impedir edição por usuário não autorizado

- Resultado esperado:
  - Mensagem de erro

- Resultado obtido:
  - Mensagem "Você não tem permissão para editar este anúncio."
<img width="1909" height="911" alt="Captura de tela 2025-11-02 222352" src="https://github.com/user-attachments/assets/60c37bef-2310-48b2-822e-eefaf17fdfd8" />

#### CT-011 — Excluir anúncio válido

- Resultado esperado:
  - Retorno 200/204
  - Item removido da listagem

- Resultado obtido:
  - Retorno 200/204
  - Item removido da listagem
<img width="1897" height="925" alt="Captura de tela 2025-11-03 145119" src="https://github.com/user-attachments/assets/5a4b4bf6-0ab4-4f2b-849d-e1a01283117f" />

### RF-003 — Detalhamento de Anúncio
#### CT-012 — Exibir detalhes completos

- Objetivo: Garantir todas as informações do anúncio.

- Resultado esperado:
  - Título, autor, fotos, descrição, avaliações, comentários

- Resultado obtido:
  - Título, autor, fotos, descrição, avaliações, comentários
<img width="1900" height="864" alt="Captura de tela 2025-11-03 140618" src="https://github.com/user-attachments/assets/bf659abf-722e-41b5-9ac1-2ea316b597ee" />

#### CT-013 — Anúncio inexistente

- Resultado esperado:
  - Erro 404
  - Tela de “não encontrado”

- Resultado obtido:
  - Erro 404
  - Tela de “não encontrado”
<img width="1908" height="943" alt="Captura de tela 2025-11-02 222725" src="https://github.com/user-attachments/assets/21bb4891-bd4f-499f-bb58-f19715ea3d70" />
    
#### CT-014 — Responsividade da página de detalhes

- Objetivo: Atender RNF-002.

- Resultado esperado:
  - Layout adaptado a smartphone/tablet

- Resultado obtido:
  - Layout adaptado a smartphone/tablet
<img width="350" height="716" alt="Captura de tela 2025-11-03 140457" src="https://github.com/user-attachments/assets/8fec5f4f-2b9c-4bdc-9037-ff35be8535ed" />

<img width="472" height="700" alt="Captura de tela 2025-11-03 140538" src="https://github.com/user-attachments/assets/7c5bd3a5-534e-459c-8e51-b1a2d984df8e" />

#### CT-015 — Carregamento de dados

- Objetivo: Checar loaders.

- Resultado esperado:
  - Skeleton ou loading exibido
  - Dados renderizados corretamente

- Resultado obtido:
  - Skeleton ou loading exibido
  - Dados renderizados corretamente
    
### RF-004 — Busca e Filtros
#### CT-016 — Busca por título

- Resultado esperado:
  - Anúncios relevantes exibidos

- Resultado obtido:
  - Anúncios relevantes exibidos
    <img width="1897" height="848" alt="Captura de tela 2025-11-02 222823" src="https://github.com/user-attachments/assets/b512b1c9-7b62-496e-8677-d45ebb6a065b" />

#### CT-017 — Filtro por gênero

- Resultado esperado:
  - Listagem filtrada

- Resultado obtido:
  - Listagem filtrada

<img width="1896" height="847" alt="Captura de tela 2025-11-02 222906" src="https://github.com/user-attachments/assets/92e18527-7ce0-4f86-9e36-36c1233bae9c" />

#### CT-018 — Busca sem resultados

- Resultado esperado:
  - Nenhum resultado na tela

- Resultado obtido:
  - Nenhum resultado na tela
    
<img width="1892" height="841" alt="Captura de tela 2025-11-02 222947" src="https://github.com/user-attachments/assets/4803d2a4-5aab-4841-92a3-24566ce28db7" />

#### CT-019 — Tempo da busca (RNF-004)

- Objetivo: Performance.

- Resultado esperado:
  - Resposta ≤ 2 segundos

- Resultado obtido:
  - Resposta ≤ 2 segundos
    
### RF-005 — Comentários
#### CT-020 — Criar comentário válido

- Resultado esperado:
  - Inserido e exibido imediatamente

- Resultado obtido:
  - Inserido e exibido imediatamente
<img width="1898" height="855" alt="Captura de tela 2025-11-03 140023" src="https://github.com/user-attachments/assets/458fd9bb-b2fd-494b-8eb8-8de2ef214f2c" />

#### CT-021 — Comentário inválido

- Entradas: vazio, 1 caractere, > limite.

- Resultado esperado:
  - Comentário rejeitado com aviso

- Resultado obtido:
  - Comentário rejeitado com aviso
<img width="1887" height="963" alt="Captura de tela 2025-11-03 140215" src="https://github.com/user-attachments/assets/219a4127-30db-475f-8fec-70f5ada866f7" />

#### CT-022 — Listar comentários

- Resultado esperado:
  - Ordem correta (mais recente primeiro)

- Resultado obtido:
  - Ordem correta (mais recente primeiro)
    
#### CT-023 — Excluir comentário

- Resultado esperado:
  - Comentário removido

- Resultado obtido:
  - Comentário removido
    
#### CT-024 — Muitos comentários

- Resultado esperado:
  - Paginação ou scroll funcionando

- Resultado obtido:
  - Paginação ou scroll funcionando

### RF-006 — Avaliação
#### CT-025 — Avaliação válida

- Resultado esperado:
  - Avaliação adicionada

- Resultado obtido:
  - Avaliação adicionada
<img width="1899" height="789" alt="Captura de tela 2025-11-03 140320" src="https://github.com/user-attachments/assets/bd7bf6c4-319a-45cf-8188-2e988033e631" />

#### CT-026 — Visualização das avaliações

- Resultado esperado:
  - Notas mostradas corretamente

- Resultado obtido:
  - Notas mostradas corretamente
    
### RNF — Usabilidade, Desempenho, Segurança, Confiabilidade
### Usabilidade
#### CT-027 — Usuário cria anúncio em < 30s

- Objetivo: RNF-001.

- Resultado:
  - Fluxo concluído dentro do tempo

#### CT-028 — Clareza dos campos

- Resultado:
  - Rótulos intuitivos

#### CT-029 — Tempo total do fluxo

- Resultado:
  - Menos passos possíveis

### Responsividade
#### CT-030 — Responsividade smartphone pequeno
#### CT-031 — Responsividade smartphone padrão
#### CT-032 — Responsividade tablet

- Resultado:
  - Tela ajusta sem quebrar layout

<p align="center"> <img width="278" height="570" alt="Captura de tela 2025-11-02 223150" src="https://github.com/user-attachments/assets/e1f1af5b-13a0-43ab-bdfa-a032fc356d5e" />

<p align="center"> <img width="384" height="706" alt="Captura de tela 2025-11-02 223104" src="https://github.com/user-attachments/assets/8f718ca0-d3d2-47a4-85c0-1e019edddb27" />

<p align="center"> <img width="572" height="778" alt="Captura de tela 2025-11-02 223304" src="https://github.com/user-attachments/assets/4ee9328d-8425-4444-8a39-25475642385b" />

### Feedback Visual
#### CT-033 — Feedback para erros

- Resultado:
  - Toasts/modais/alerts corretos

### Desempenho
#### CT-034 — Performance da busca

- Resultado:
  - ≤ 2 segundos

#### CT-035 — Stress da busca

- Resultado:
  - Sistema continua respondendo

#### CT-036 — Performance detalhes do anúncio

- Resultado:
  - ≤ 3 segundos

#### CT-037 — Performance perfil

- Resultado esperado:
  - ≤ 3 segundos

### Segurança
#### CT-038 — Hash da senha

- Resultado:
  - Senha não está em texto puro

#### CT-039 — Testar se senha nunca trafega no front

- Resultado:
  - Nenhum retorno contém senha

### Confiabilidade
#### CT-040 — Estabilidade prolongada

- Resultado:
  - Sistema funcionando por horas sem queda

#### CT-041 — Teste de reincidência de falhas

- Resultado:
  - Sistema se recupera sem corromper dados

#### CT-042 — Evitar duplicação em operações

- Resultado:
  - Mesma ação não executa duas vezes
    
# Referências

Angular: https://angular.dev/overview
<br> TypeScript: https://www.typescriptlang.org/docs/

# Planejamento

##  Quadro de tarefas

> Apresente a divisão de tarefas entre os membros do grupo e o acompanhamento da execução, conforme o exemplo abaixo.

#### Semana 2

Atualizado em: 02/11/2025

| Responsável       | Tarefa/Requisito                                                                                        | Iniciado em |    Prazo   | Status | Terminado em |
| :---------------- | :------------------------------------------------------------------------------------------------------ | :---------: | :--------: | :----: | :----------: |
| Rômulo Ferraz     | Login, Cadastro, Página Inicial, Página do Anúncio, Página de edição do anúncio, Components, Interceptor, Estilos globais, Página do Usuário, SiteService, Routes, LoadingDirective, configuração do ambiente (frontend). (texto, estilo e funcionalidades). Documentação: Front-end Web, Projeto da Interface Web, Wireframes, Design Visual, Fluxo de Dados, Tecnologias Utilizadas, Considerações de Segurança   |  01/10/2025 | 02/11/2025 |   ✔️   |  02/11/2025  |
| Isadora Carvalho            | Responsividade das páginas, funcionalidade de excluir comentários criados apenas pelo usuário logado, casos de teste e documentação.                                                                                           |  01/10/2025 | 02/11/2025 |   ✔️   | 02/11/2025             |
| Giulia Fernandes           | Responsividade e design das páginas.                                                                                         |  01/10/2025 | 02/11/2025 |   ✔️   | 02/11/2025             |
| Samuel            | Edição do template para incluir as imagens na home, edição e detalhes, e parte da documentação.                                                                                         |  01/10/2025 | 02/11/2025 |   ✔️   |              |
| Rafael            | Página de criação de anúncios.                                                                                         |  01/10/2025 | 02/11/2025 |   ✔️   |              |
| Jaime            |                                                                                          |  01/10/2025 | 02/11/2025 |   📝   |              |

Legenda:
- ✔️: terminado
- 📝: em execução
- ⌛: atrasado
- ❌: não iniciado
