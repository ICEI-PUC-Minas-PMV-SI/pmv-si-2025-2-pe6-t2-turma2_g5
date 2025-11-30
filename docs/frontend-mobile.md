# Front-end Móvel

A Estante Infinita nasce como resposta ao cenário em que o preço elevado dos livros se impõe como barreira ao acesso à leitura. A proposta visa democratizar o acesso ao conhecimento por meio de um marketplace digital que privilegia a compra de livros usados, a troca entre usuários e a doação, ampliando o ciclo de vida dos acervos e reduzindo custos. O público-alvo são jovens e adultos a partir de 18 anos, estudantes e leitores engajados em práticas de consumo consciente e sustentável, que veem na leitura não apenas lazer, mas também oportunidade de formação cultural e acadêmica.

Para apoiar essa iniciativa, foi desenvolvida um aplicativo mobile desenvolvido com React Native, Expo e TypeScript, foi estruturado uma camada de comunicação que centraliza todas as solicitações ao backend em Express hospedado na Vercel.

O aplicativo foi projetado para oferecer aos usuários uma navegação simples, responsiva e intuitiva, permitindo acesso rápido às principais funcionalidades da plataforma diretamente pelo smartphone. <br>

O objetivo deste front-end mobile é ampliar a acessibilidade do sistema, permitindo que cada usuário crie, gerencie e visualize anúncios de forma prática, além de interagir com outros participantes por meio de comentários e demonstrações de interesse — tudo em uma interface amigável e pensada para uso cotidiano.

### Objetivos específicos do Front-end Mobile:

Gerenciamento de anúncios (CRUD): permitir criar, editar, listar e visualizar anúncios no celular, de forma simples e eficiente. <br>

Interação e engajamento: possibilitar que usuários comentem nos anúncios, manifestem interesse e acompanhem atualizações em tempo real. <br>

Experiência mobile-first: oferecer uma interface adaptada especialmente para telas pequenas, priorizando usabilidade, legibilidade e fluidez. <br>

Integração com o Backend: garantir comunicação eficiente via API, mantendo sincronização contínua entre aplicativo e servidor. <br>

Performance e otimização: utilizar recursos nativos do React Native para garantir rapidez, renderização otimizada e uma experiência consistente. <br>

### Stack utilizada:

Framework: React Native <br>

Linguagem: TypeScript

## Projeto da Interface
A interface móvel da Estante Infinita foi desenvolvida utilizando React Native, priorizando uma experiência fluida, intuitiva e otimizada para dispositivos móveis. O design segue a mesma identidade visual da versão web, mantendo uma estética minimalista, com predominância de tons branco, preto e magenta, garantindo consistência entre as plataformas e proporcionando uma navegação agradável e moderna.

O layout foi projetado com foco em mobile-first, utilizando componentes nativos, navegação empilhada e menus contextuais, garantindo boa legibilidade, hierarquia clara das informações e interações rápidas para o usuário.

### Principais Telas e Interações:

Home: tela inicial que exibe apresenta os anúncios disponíveis. O usuário pode navegar pelos itens, utilizar a barra de pesquisa e acessar filtros como gênero literário. O layout prioriza cartões de anúncios organizados em lista vertical, garantindo visual limpo e toque rápido.

Login e Registro: telas de autenticação implementadas com validação de campos e comunicação com a API. Após login bem-sucedido, o token e os dados do usuário são armazenados para permitir acesso seguro às funcionalidades restritas. A tela de registro permite criar uma nova conta com nome, e-mail e senha, oferecendo feedbacks visuais e navegação direta entre login e cadastro.

Book Page (Detalhes do Anúncio): apresenta informações detalhadas sobre o livro selecionado, incluindo descrição, autor, gênero e área dedicada a comentários. Os usuários podem manifestar interesse no anúncio e interagir com o proprietário diretamente pela interface, com atualização dinâmica das interações.

Profile Page: área exclusiva para o usuário autenticado, onde é possível gerenciar seus próprios anúncios. Permite editar, excluir e visualizar interações e comentários recebidos. A interface utiliza componentes como botões para criação de novos anúncios, facilitando ações rápidas.

### Wireframes

<img width="1536" height="1024" alt="wireframe" src="https://github.com/user-attachments/assets/219bb19d-06b9-4698-a2b0-f0fab2039487" />

### Design Visual

Minimalista, moderno e limpo. O design prioriza a legibilidade e a organização, utilizando um layout estruturado e um uso generoso de espaço em branco para evitar poluição visual.

Paleta de Cores: A paleta é primariamente neutra, com um único e forte ponto de cor para destaque e identidade. Branco e Cinza Claro: O fundo principal da área de conteúdo é branco, enquanto o "hero banner" (a faixa superior) usa um tom de cinza muito claro na borda. Isso cria uma base suave e limpa. Preto e Cinza Escuro: Usados para a maior parte da tipografia (títulos, textos, nomes de autores) e para os ícones. Garantem alto contraste e excelente legibilidade. 

Tipografia: A tipografia é inteiramente sans-serif (sem serifa), o que contribui para a sensação de modernidade e clareza. Hierarquia: Há uma hierarquia visual clara. Títulos principais (como "Estante Infinita" e os títulos dos livros, ex: "Duna") usam um peso bold (negrito) e um tamanho de fonte maior. Texto de Apoio: O subtítulo e as descrições dos livros usam um peso de fonte mais leve (regular ou light) e um tamanho menor, facilitando a diferenciação entre título e conteúdo. 

Ícones e Elementos Gráficos: Os ícones e elementos gráficos são simples e consistentes, reforçando o minimalismo.Ícones de Categoria: Ícones de UI: Ícones de interface padrão, como o ícone de busca (lupa) na barra de pesquisa segue o estilo de contorno e simplicidade. Esta é uma escolha de design inteligente que conecta o conteúdo diretamente ao nome da marca ("Estante Infinita").

Layout e Outros Elementos: Layout em Grade (Grid): O conteúdo principal, especialmente a lista de livros, é organizado em um sistema de grade (cards). Isso cria uma sensação de ordem, alinhamento e facilita a varredura visual. Espaço em Branco: O uso de espaço em branco (ou espaço negativo) é fundamental neste design. Ele separa claramente a seção de categorias, a barra de pesquisa e a lista de livros, permitindo que cada elemento "respire". Cards de Livro: Cada livro é apresentado em um "card" individual. Este card contém a imagem, título, autor, uma breve descrição e a etiqueta de categoria colorida. Barra de Pesquisa: É um elemento simples, com cantos arredondados e um ícone claro, integrando-se de forma suave ao restante do layout.

<p align="center">
  <img width="250" height="550" src="https://github.com/user-attachments/assets/eacf7a02-8026-4846-ba02-09e4cf1670f1">
</p>
<br>
<p align="center">
  <img width="250" height="550" src="https://github.com/user-attachments/assets/4ca9295d-75d6-4fa9-a28c-c90d9d2e2265">
</p>
<br>
<p align="center">
  <img width="250" height="550" src="https://github.com/user-attachments/assets/63e3cd25-4ae7-4d45-a2d2-6527cdd71735">
</p>
<br>

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

https://express-js-on-vercel-ten-cyan.vercel.app

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

Atualizado em: 29/11/2025

| Responsável   | Tarefa/Requisito | Iniciado em    | Prazo      | Status | Terminado em    |
| :----         |    :----         |      :----:    | :----:     | :----: | :----:          |
| Rômulo Ferraz | Login, Registro e Adição de comentários | 10/11/2025     | 21/11/2025 | ✔️    | 21/11/2025      |
| Isadora Aparecida| Objetivos, Projeto da Interface, Wireframes, Design Visual | 03/11/2025 | 30/11/2025 | ✔️ | 29/11/2025 |
| AlunoY        | Histórias de usuário  | 01/01/2024     | 07/01/2005 | ⌛     |                 |
| AlunoK        | Personas 1  |    01/01/2024        | 12/02/2005 | ❌    |       |


Legenda:
- ✔️: terminado
- 📝: em execução
- ⌛: atrasado
- ❌: não iniciado

