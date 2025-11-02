# Front-end Web

Frontend Angular para um marketplace de anúncios com suporte a SSR (Angular Universal).

Objetivo: permitir autenticação (registro/login) e CRUD completo de anúncios (criar, editar, listar, visualizar) com possibilidade do usuário inserir comentários em cada um desses anúncios, demonstrando seu interesse nos mesmos.
Principais pontos: interceptor de auth, componentes reutilizáveis (header/footer), SSR para SEO.
Stack: Angular, TypeScript.
Como rodar (dev): execute npm install e depois ng serve.

## Projeto da Interface Web

A interface web foi desenvolvida utilizando o framework Angular, priorizando um design responsivo e minimalista. A paleta de cores é composta por tons de azul e branco, transmitindo clareza e profissionalismo.
O layout segue uma estrutura com cabeçalho fixo, menu lateral e área principal de conteúdo. Na página inicial, o usuário visualiza uma lista de anúncios com opções de filtragem e busca. Ao clicar em um item, é redirecionado para a página de detalhes.
As interações incluem feedback visual em todas as ações, como mensagens de sucesso ou erro. O design foi pensado para oferecer uma navegação simples e intuitiva.

### Wireframes

<img width="617" height="769" alt="image" src="https://github.com/user-attachments/assets/adcd3e89-a426-4ef9-ba9e-0d5481a085f4" />

<img width="618" height="625" alt="image" src="https://github.com/user-attachments/assets/20bcfb94-5b52-48b3-b279-78aacb8fc7d1" />

<img width="615" height="386" alt="image" src="https://github.com/user-attachments/assets/dec52594-cac6-4cf2-9610-8337da2b3e42" />


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
  origin: "https://seu-dominio.com",
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

[Instruções para implantar a aplicação distribuída em um ambiente de produção.]

1. Defina os requisitos de hardware e software necessários para implantar a aplicação em um ambiente de produção.
2. Escolha uma plataforma de hospedagem adequada, como um provedor de nuvem ou um servidor dedicado.
3. Configure o ambiente de implantação, incluindo a instalação de dependências e configuração de variáveis de ambiente.
4. Faça o deploy da aplicação no ambiente escolhido, seguindo as instruções específicas da plataforma de hospedagem.

## Testes

[Descreva a estratégia de teste, incluindo os tipos de teste a serem realizados (unitários, integração, carga, etc.) e as ferramentas a serem utilizadas.]

1. Crie casos de teste para cobrir todos os requisitos funcionais e não funcionais da aplicação.
2. Implemente testes unitários para testar unidades individuais de código, como funções e classes.
3. Realize testes de integração para verificar a interação correta entre os componentes da aplicação.
4. Execute testes de carga para avaliar o desempenho da aplicação sob carga significativa.
5. Utilize ferramentas de teste adequadas, como frameworks de teste e ferramentas de automação de teste, para agilizar o processo de teste.

# Referências

NA

# Planejamento

##  Quadro de tarefas

> Apresente a divisão de tarefas entre os membros do grupo e o acompanhamento da execução, conforme o exemplo abaixo.

#### Semana 2

Atualizado em: 02/11/2025

| Responsável       | Tarefa/Requisito                                                                                        | Iniciado em |    Prazo   | Status | Terminado em |
| :---------------- | :------------------------------------------------------------------------------------------------------ | :---------: | :--------: | :----: | :----------: |
| Rômulo Ferraz     | Login, Cadastro, Página Inicial, Página do Anúncio, Página de edição do anúncio, Components, Interceptor, Estilos globais, Página do Usuário, SiteService, Routes, LoadingDirective, configuração do ambiente (frontend). (texto, estilo e funcionalidades). Documentação: Front-end Web, Projeto da Interface Web, Wireframes, Design Visual, Fluxo de Dados, Tecnologias Utilizadas, Considerações de Segurança   |  01/10/2025 | 25/10/2025 |   ✔️   |  05/02/2024  |
| AlunaZ            | CSS unificado                                                                                           |  03/02/2024 | 10/03/2024 |   📝   |              |
| AlunoY            | Página de login                                                                                         |  01/02/2024 | 07/03/2024 |   ⌛   |              |
| AlunoK            | Script de login                                                                                         |  01/01/2024 | 12/03/2024 |   ❌   |              |


Legenda:
- ✔️: terminado
- 📝: em execução
- ⌛: atrasado
- ❌: não iniciado

