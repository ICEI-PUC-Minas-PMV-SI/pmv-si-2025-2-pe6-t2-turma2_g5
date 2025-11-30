# Front-end Móvel

A Estante Infinita nasce como resposta ao cenário em que o preço elevado dos livros se impõe como barreira ao acesso à leitura. A proposta visa democratizar o acesso ao conhecimento por meio de um marketplace digital que privilegia a compra de livros usados, a troca entre usuários e a doação, ampliando o ciclo de vida dos acervos e reduzindo custos. O público-alvo são jovens e adultos a partir de 18 anos, estudantes e leitores engajados em práticas de consumo consciente e sustentável, que veem na leitura não apenas lazer, mas também oportunidade de formação cultural e acadêmica.

Para apoiar essa iniciativa, foi desenvolvida um aplicativo mobile desenvolvido com React Native, Expo e TypeScript, foi estruturado uma camada de comunicação que centraliza todas as solicitações ao backend em Express hospedado na Vercel.

## Projeto da Interface
[Descreva o projeto da interface móvel da aplicação, incluindo o design visual, layout das páginas, interações do usuário e outros aspectos relevantes.]

### Wireframes

[Inclua os wireframes das páginas principais da interface, mostrando a disposição dos elementos na página.]

### Design Visual

[Descreva o estilo visual da interface, incluindo paleta de cores, tipografia, ícones e outros elementos gráficos.]

## Fluxo de Dados

[Diagrama ou descrição do fluxo de dados na aplicação.]

## Tecnologias Utilizadas

[Lista das tecnologias principais que serão utilizadas no projeto.]

- React Native: base do aplicativo mobile, responsável pelos componentes de interface e pela renderização nativa nas telas em app/ e nos componentes em components/.

- Expo: gerencia o ambiente de desenvolvimento e build (expo start nos scripts do package.json) e integra recursos nativos (StatusBar, etc.). O ponto de entrada é o expo-router/entry.

- TypeScript: tipagem estática em praticamente todo o código (.ts e .tsx), incluindo hooks (hooks/useBooks.ts), contexto de autenticação (contexts/AuthContext.tsx), serviços e tipos em lib/types.ts.

- expo-router: faz o roteamento baseado em arquivos na pasta app/ (_layout.tsx, index.tsx, grupos de rotas, etc.), controlando navegação entre telas e fluxos autenticados/não autenticados.

- React Navigation (@react-navigation/native): integrado ao expo-router para prover o ThemeProvider e a navegação com tema (NAV_THEME em lib/theme.ts) no layout raiz (app/_layout.tsx).

- Axios: em services/api.ts é criado o apiClient com baseURL vinda de BASE_API_URL (lib/constants.ts). Há um interceptor que lê o token armazenado e adiciona Authorization: Bearer <token> em todas as requisições.

- AsyncStorage (@react-native-async-storage/async-storage): garante que o usuário continue autenticado entre aberturas do app.

- Context API (AuthContext): contexts/AuthContext.tsx centraliza estado de autenticação (user, token, loading, signIn, signOut, etc.). Envolve a árvore de componentes (via AuthProvider em _layout.tsx), permitindo que telas e hooks acessem useAuth().


## Considerações de Segurança

A única medida de segurança implementada será de garantir que todas as informações de autenticação do usuário, como senhas, serão armazenadas no banco de dados de forma criptografada. Não haverá, neste momento, controles adicionais de autorização granular, proteção contra ataques ou hardening de infraestrutura.

## Implantação

[Instruções para implantar a aplicação distribuída em um ambiente de produção.]

1. Defina os requisitos de hardware e software necessários para implantar a aplicação em um ambiente de produção.
2. Escolha uma plataforma de hospedagem adequada, como um provedor de nuvem ou um servidor dedicado.
3. Configure o ambiente de implantação, incluindo a instalação de dependências e configuração de variáveis de ambiente.
4. Faça o deploy da aplicação no ambiente escolhido, seguindo as instruções específicas da plataforma de hospedagem.
5. Realize testes para garantir que a aplicação esteja funcionando corretamente no ambiente de produção.

## Testes
Os testes funcionais realizados são cruciais porque validam se o app cumpre o que promete ao usuário. Reduzindo risco de regressões e servem como evidência de qualidade, dessa forma, seguem vídeo dos testes realizados:

|Testes Funcionais           | Objetivo                 |           Comprovação |
|---------------------------|------------|--------------|
| Login/Logout              | **Verificar** o acesso e a saída do perfil, e que o sistema apresente uma mensagem de erro ao inserir credenciais incorretas. | [Teste Login/Logout](https://youtube.com/shorts/ALd58aVlsDI?feature=share) |
| Login                     | **Validar** o comportamento do sistema ao tentar fazer login com um usuário inexistente, esperando a exibição de uma mensagem de erro. | [Teste Login (ERRO)](https://youtube.com/shorts/QTc7n1b-WRw) |
| Cadastro                  | **Testar** o fluxo completo de cadastro de um novo perfil de usuário. | [Teste Cadastro](https://youtube.com/shorts/y67OkBwByl8) |
| Cadastro                  | **Garantir** que o sistema impeça o cadastro de um novo perfil utilizando um e-mail já existente, exibindo erro. | [Teste Cadastro (ERRO)](https://youtube.com/shorts/tczVXXS1LUs) |
| Cadastro                  | **Confirmar** que o sistema exige o preenchimento de todos os campos obrigatórios para a conclusão do cadastro, impedindo a submissão incompleta. | [Teste Cadastro (ERRO)](https://youtube.com/shorts/tczVXXS1LUs) |
| Comentário                | **Avaliar** as funcionalidades de criação, edição e exclusão de comentários, além de **verificar** as restrições de permissão (não permitir editar/excluir comentários de outros usuários). | [Teste Comentário](https://youtube.com/shorts/LyCj__Z6S2I) |
| Anuncio                     | **Verificar** se todos os anúncios cadastrados são listados corretamente na interface. | [Listagem Anuncio](https://youtube.com/shorts/0YdXlSAFCDs) |
| Anuncio                     | **Testar** a busca por anúncios utilizando IDs válidos e inválidos para **confirmar** o retorno esperado em ambos os cenários. | [Buscar Anuncio](https://youtube.com/shorts/t_5iaKFQt4A) |
| Anuncio                     | **Validar** a criação de um novo anúncio e **garantir** que a publicação seja impedida caso faltem dados obrigatórios. | [Criar Anuncio](https://youtube.com/shorts/gpUKH38tkNk?feature=share) |  


# Referências

Vercel: https://vercel.com/docs

Node.js: https://nodejs.org/docs/latest/api/

TypeScript: https://www.typescriptlang.org/pt/docs/

React Native: https://reactnative.dev/docs/getting-started

Expo: https://docs.expo.dev/

TypeScript: https://www.typescriptlang.org/pt/docs/

# Planejamento

##  Quadro de tarefas

> Apresente a divisão de tarefas entre os membros do grupo e o acompanhamento da execução, conforme o exemplo abaixo.

### Semana 1

Atualizado em: 21/11/2025

| Responsável   | Tarefa/Requisito | Iniciado em    | Prazo      | Status | Terminado em    |
| :----         |    :----         |      :----:    | :----:     | :----: | :----:          |
| Rômulo Ferraz | Login, Registro e Adição de comentários | 10/11/2025     | 21/11/2025 | ✔️    | 18/02/2024      |
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

