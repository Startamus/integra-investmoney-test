# Projeto de Integração da Clínica Integra com Investmoney

Este teste técnico tem como objetivo avaliar suas habilidades em desenvolvimento front-end utilizando Svelte, com foco na implementação de rotas de autenticação e pré-cadastro, utilizando as operações HTTP `POST`, `PATCH`, `PUT` e listagem de objetos com filtros. A aplicação deve consumir a API fornecida através do Swagger JSON disponibilizado.

## Contexto do Projeto

A Investmoney é uma empresa especializada em financiamento de crédito para pacientes que necessitam realizar procedimentos médicos. A Clínica Integra, buscando ampliar o acesso aos seus serviços, estabeleceu uma parceria com a Investmoney para oferecer soluções de financiamento aos seus pacientes. Para viabilizar essa parceria, a Clínica Integra necessita de um aplicativo web que permita:

1. Realizar o pré-cadastro dos pacientes interessados em financiamento.
2. Gerenciar e acompanhar o status desses pré-cadastros.
3. Visualizar informações detalhadas sobre cada solicitação.

## Escopo do Projeto

Como desenvolvedor contratado, você deverá construir uma aplicação web utilizando o framework Svelte, contemplando:

1. **Sistema de Autenticação Completo**:
   - Implementação do login seguro utilizando as credenciais fornecidas pela clínica.
   - Gerenciamento de tokens de acesso e refresh.
   - Proteção de rotas para usuários não autenticados.
   - Funcionalidade de logout.

2. **Módulo de Pré-Cadastro de Pacientes** (CRUD completo):
   - Listagem de todos os pré-cadastros com opções de filtragem e paginação.
   - Formulário para criação de novos pré-cadastros com validação de dados.
   - Visualização detalhada das informações do pré-cadastro.
   - Edição de dados do pré-cadastro.
   - Atualização de status (pendente, registrado, rejeitado).
   - Dashboard com resumo por status.

## Recursos Disponíveis

Para o desenvolvimento deste projeto, você recebeu:

- Documentação completa da API Investmoney (Swagger):
  - ```https://investm-backend-divine-field-7851.fly.dev/```
- Credenciais de acesso (login e senha) para a Clínica Integra:
  - ```bash
    "username": "clinica.integra",
    "password": "Integra2023Secure!",
    ```
- Endpoints necessários para integração com o sistema da Investmoney.

## Entrega Esperada

- Uma aplicação web responsiva e intuitiva, desenvolvida em Svelte, que permita à equipe da Clínica Integra gerenciar eficientemente o processo de pré-cadastro de seus pacientes para financiamento médico junto à Investmoney.
- A aplicação deve seguir boas práticas de desenvolvimento, incluindo testes unitários e de integração, além de apresentar uma interface de usuário amigável e profissional.

## Requisitos

### 1. **Autenticação**
   - Implementar a funcionalidade de autenticação utilizando as rotas disponíveis no Swagger.
   - As rotas de autenticação incluem:
     - **POST** `/authentication/token/`: Gera um token de autenticação.
     - **POST** `/authentication/token/verify/`: Verifica a validade de um token.
     - **POST** `/authentication/refresh/`: Atualiza o token de acesso.
     - **POST** `/authentication/logout/`: Realiza o logout do usuário.

### 2. **Pré-Cadastro**
   - Implementar a funcionalidade de pré-cadastro utilizando as rotas disponíveis no Swagger.
   - As rotas de pré-cadastro incluem:
     - **POST** `/pre-register/`: Cria um novo pré-cadastro.
     - **PATCH** `/pre-register/{id}/`: Atualiza parcialmente um pré-cadastro existente.
     - **PUT** `/pre-register/{id}/`: Atualiza completamente um pré-cadastro existente.
     - **GET** `/pre-register/`: Lista todos os pré-cadastros, com paginação dos dados e possibilidade de filtragem por `status`, `cpf`, `name`, `email`, `phone`, `cnpj`, etc.

### 3. **Listagem com Filtros**
   - Implementar a listagem de objetos com filtros, utilizando os parâmetros de query disponíveis nas rotas.
   - Exemplo de filtros:
     - **GET** `/assignor/`: Lista todos os cedentes, com filtros por `cnpj`, `fantasy_name`, `social_reason`, `email`, `phone`, etc.
     - **GET** `/pre-register/`: Lista todos os pré-cadastros, com filtros por `status`, `cpf`, `name`, `email`, `phone`, etc.

### 4. **Interface de Usuário**
   - Criar uma interface de usuário intuitiva e responsiva para as funcionalidades de autenticação e pré-cadastro.
   - A interface deve permitir:
     - Login e logout.
     - Criação, edição e listagem de pré-cadastros.
     - Filtragem de listagens conforme os parâmetros disponíveis.
       
### 5. **Procedimentos**
   - Essas rotas serao usadas para listar os procedimentos da sua clinica.
   - **GET** `/assignor/procedure/`: Lista todos os procedimentos do cedente
   - **GET** `/assignor/procedure/{id}`: Lista  o procedimento do cedente pelo id
### 6. **Categorias**
   - Essas rotas serao usadas para listar os categorias  que um procediemnto pode possuir.
   - **GET** `/assignor/procedure-category/`: Lista todos os procedimentos do cedente.
   - **GET** `/assignor/procedure-category/{id}`: Lista  a categoria de procedimento pelo id

## Tecnologias

- **Svelte**: Framework principal para desenvolvimento front-end.
- **SvelteKit**: Para roteamento e gerenciamento de páginas.
- **Tailwind CSS**: Para estilização.
- **Axios** ou **Fetch API**: Para consumo da API.
- **JWT**: Para gerenciamento de autenticação.

## Entregáveis

1. **Código Fonte**: Todo o código fonte da aplicação, incluindo componentes, rotas, serviços e estilos.
2. **Instruções de Execução**: Um arquivo `README.md` com instruções claras para execução do projeto localmente.
3. **Testes**: Testes unitários e/ou de integração para as funcionalidades implementadas.
4. **Deploy**: Opcionalmente, um link para a aplicação em produção (ex: Vercel, Netlify, etc.).

## Avaliação

- **Funcionalidade**: A aplicação deve cumprir todos os requisitos funcionais descritos.
- **Qualidade do Código**: O código deve ser limpo, bem organizado e seguir boas práticas de desenvolvimento.
- **Interface de Usuário**: A interface deve ser intuitiva, responsiva e seguir boas práticas de UX/UI.
- **Testes**: A cobertura de testes será avaliada, com foco em garantir a qualidade e a robustez do código.

## Dicas

- Utilize o Swagger UI para explorar a API e entender as rotas disponíveis.
- Considere a criação de um serviço separado para o consumo da API, facilitando a manutenção e a reutilização do código.
- Documente seu código e utilize comentários quando necessário para explicar decisões de implementação.

## Testes

A aplicação deve incluir testes unitários e de integração para garantir a qualidade e a robustez do código. Abaixo estão as diretrizes gerais para a implementação dos testes.

### 1. **Testes Unitários**

Os testes unitários devem focar em testar componentes, funções e serviços de forma isolada. Eles devem garantir que cada parte da aplicação funcione corretamente individualmente.

#### O que testar:
- **Componentes**: Verifique se os componentes renderizam corretamente e se respondem adequadamente a interações do usuário (cliques, entradas de formulário, etc.).
- **Serviços**: Teste as funções que fazem chamadas à API, garantindo que elas lidem corretamente com sucesso, erros e edge cases.
- **Funções utilitárias**: Teste funções auxiliares que realizam lógica de negócio, como validação de dados, formatação, etc.

#### Ferramentas sugeridas:
- **Jest** ou **Vitest** para testes unitários.
- **Testing Library** para testar componentes Svelte.

---

### 2. **Testes de Integração**

Os testes de integração devem garantir que as diferentes partes da aplicação funcionem corretamente juntas. Eles devem simular o fluxo completo do usuário, desde a interação com a interface até a comunicação com a API.

#### O que testar:
- **Fluxos de autenticação**: Verifique se o login, logout e renovação de token funcionam conforme esperado.
- **Fluxos de pré-cadastro**: Teste a criação, edição e listagem de pré-cadastros, incluindo a interação com a API.
- **Filtros e listagens**: Garanta que a aplicação filtre e liste os dados corretamente com base nos parâmetros fornecidos.

#### Ferramentas sugeridas:
- **Testing Library** para simular interações do usuário.
- **Mock de APIs**: Utilize mocks para simular respostas da API e testar cenários de sucesso e erro.

---

### 3. **Cobertura de Testes**

A cobertura de testes deve ser abrangente, garantindo que a maior parte do código seja testada. Utilize ferramentas como **Istanbul** ou a cobertura nativa do Jest/Vitest para monitorar a cobertura.

#### O que priorizar:
- **Funcionalidades críticas**: Teste exaustivamente as funcionalidades principais, como autenticação e pré-cadastro.
- **Edge cases**: Garanta que a aplicação lide corretamente com cenários inesperados, como entradas inválidas ou falhas na API.

---

### 4. **Execução dos Testes**

Inclua scripts no `package.json` para facilitar a execução dos testes. Exemplo:

```json
"scripts": {
  "test": "vitest run",
  "test:watch": "vitest",
  "test:coverage": "vitest run --coverage"
}
```

---

### 5. **Boas Práticas**

- **Mantenha os testes isolados**: Cada teste deve ser independente e não depender do estado de outros testes.
- **Use mocks e stubs**: Simule dependências externas, como chamadas à API, para garantir que os testes sejam confiáveis e rápidos.
- **Teste cenários de erro**: Garanta que a aplicação lide corretamente com erros, como falhas na API ou entradas inválidas.
- **Documente os testes**: Adicione descrições claras aos testes para facilitar a manutenção.

---

## Exemplo de Estrutura de Projeto

```plaintext
svelte-app/
├── src/
│   ├── lib/
│   │   ├── services/
│   │   │   ├── authService.js
│   │   │   ├── preRegisterService.js
│   ├── routes/
│   │   ├── login/
│   │   │   ├── +page.svelte
│   │   ├── pre-register/
│   │   │   ├── +page.svelte
│   │   │   ├── [id]/
│   │   │   │   ├── +page.svelte
│   ├── components/
│   │   ├── Header.svelte
│   │   ├── Footer.svelte
│   │   ├── PreRegisterForm.svelte
│   ├── app.html
│   ├── app.postcss
└── tests/
    ├── unit/
    │   ├── components/
    │   ├── services/
    │   └── stores/
    └── e2e/
        ├── list.test.js
        ├── create.test.js
        ├── update.test.js
        └── dashboard.test.js
├── README.md
├── package.json
```

---

Este texto está mais conciso, com redundâncias removidas e informações organizadas de forma clara e direta. Se precisar de mais ajustes, é só avisar!
