# Apresentação da Solução

O desenvolvimento do projeto Estante Infinita permitiu à equipe explorar tecnologias modernas e consolidadas no mercado, integrando aplicações web, mobile e backend em um ecossistema distribuído. Nesta seção, são apresentadas as considerações finais sobre o uso das tecnologias escolhidas, a arquitetura do sistema, o processo de desenvolvimento, bem como o estado atual da colaboração no GitHub e as responsabilidades de cada membro da equipe. A seguir, o vídeo e slides de apresentação: 


https://github.com/user-attachments/assets/166e3969-2e7e-4923-828f-3a9c0fc8a216

[apresentação final - estante infinita.pptx](https://github.com/user-attachments/files/24020297/apresentacao.final.-.estante.infinita.pptx) <br>
[apresentação final - estante infinita.pdf](https://github.com/user-attachments/files/24020300/apresentacao.final.-.estante.infinita.pdf)

# 1. Considerações Finais

## 1.1 Avaliação dos Frameworks e Tecnologias Utilizadas

### Front-end Web — Angular + TypeScript
O uso do Angular proporcionou uma estrutura organizada baseada em módulos, componentes e serviços, o que favoreceu escalabilidade e manutenibilidade. O TypeScript ampliou a segurança do código e facilitou o desenvolvimento em equipe.

**Aspectos positivos:**
- Estrutura robusta e opinativa;
- Forte tipagem;
- Boa integração com ferramentas de build e testes.

**Desafios:**
- Curva de aprendizado maior;
- Necessidade de configurações adicionais para pequenas funcionalidades.

---

### Aplicativo Mobile — React Native
O React Native permitiu criar um aplicativo multiplataforma com agilidade, utilizando a mesma base de código em Android e iOS. O hot reload acelerou o processo de desenvolvimento e testes.

**Aspectos positivos:**
- Desenvolvimento rápido e reutilização de componentes;
- Ecossistema amplo de bibliotecas;
- Integração simples com APIs REST.

**Desafios:**
- Dependências que exigem compatibilidade frequente;
- Ajustes específicos para cada sistema operacional.

---

### Backend — Node.js + Prisma ORM + Supabase
A combinação de Node.js com Prisma ORM trouxe velocidade no desenvolvimento, tipagem automática e migrações claras e seguras. O Supabase simplificou banco de dados e armazenamento, reduzindo custos e complexidade operacional.

**Aspectos positivos:**
- Prisma rápido, versátil e com excelente documentação;
- Supabase com painel de gerenciamento intuitivo;
- Backend consistente e bem segmentado.

**Desafios:**
- Falta de padronização avançada de DTOs e validação de dados.

---

## 1.2 Análise Crítica da Arquitetura do Projeto
A arquitetura adotada — com aplicações separadas para Web, Mobile e Backend — proporcionou modularidade e permitiu que as equipes trabalhassem em paralelo. O backend expôs uma API REST clara e acessível, facilitando a integração entre os módulos.

**Pontos fortes:**
- Separação clara de responsabilidades;
- Escalabilidade facilitada;
- Reutilização de regras de negócio no backend.

**Pontos de melhoria:**
- Documentação de API via Swagger/OpenAPI;
- Organização do backend por domínios (Domain-Driven Style);
- Uso de cache (Redis) para otimizar listagens;
- Configuração de pipelines de CI/CD.

---

## 1.3 Processo de Desenvolvimento e Gestão do Trabalho

A equipe fez reuniões semanais para organizar tarefas e acompanhar o progresso do desenvolvimento.

### Retrato Atual do Quadro 
- **Backlog:** pendências de melhoria, refatoração e documentação;
- **Em andamento:** ajustes finais nas aplicações;
- **Concluídas:**  
  - CRUDs principais  
  - Integração com Supabase  
  - Desenvolvimento do front-end Web  
  - Desenvolvimento do aplicativo Mobile  
  - API e rotas essenciais  
  - Documentação técnica
| Membro               | Contribuições Principais                                                             |
| -------------------- | ------------------------------------------------------------------------------------ |
| **Giulia Mattos**    | Documentação, revisão, colaboração no front-end, e mobile, testes do mobile                                      |
| **Isadora Cardoso**  | Banco de dados (Prisma/Supabase), responsividade no Front-end Angular, testes do frontend, wireframe e design mobile |
| **Jaime Bispo**      | Documentação, modelagem de dados e ajustes técnicos                                      |
| **Rafael Fernandes** | Backend, modelagem inicial do banco, rotas, testes do backend e documentação                                            |
| **Rômulo Chaves**    | Documentação, desenvolvimento das principais funcinalidades do backend, frontend e mobile, desing web|
| **Samuel Marques**   | Banco de dados, desenvolvimento Mobile e ajustes finais                                                      |


![Quadro do GitHub Project<img width="1123" height="856" alt="Captura de tela 2025-12-07 191959" src="https://github.com/user-attachments/assets/8ea1750b-26c7-4d98-95fa-0228c6e3a96c" />

## 1.4 Considerações Finais

O projeto cumpriu seus objetivos principais, demonstrando a capacidade da equipe de trabalhar com tecnologias modernas e desenvolver um sistema completo envolvendo Web, Mobile e Backend.

A experiência proporcionou desenvolvimento técnico significativo, especialmente no uso de Angular, React Native, Node.js, Prisma e Supabase.

As melhorias sugeridas servem como guia para evolução futura do projeto, garantindo maior robustez, escalabilidade e profissionalismo em versões futuras.


