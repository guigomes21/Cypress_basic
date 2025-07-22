# 🧪 Cypress E2E Testing

Este projeto utiliza o [Cypress](https://www.cypress.io/) para realizar testes end-to-end de forma rápida, confiável e interativa. Com ele, é possível validar o funcionamento da aplicação simulando interações reais de um usuário.

## 📦 Requisitos

- [Node.js](https://nodejs.org/) (recomendado: versão LTS)
- [npm](https://www.npmjs.com/) ou [Yarn](https://yarnpkg.com/)

> Verifique a instalação com:
```bash
node -v
npm -v
```

---

## 🚀 Instalação

1. Clone o repositório (caso ainda não tenha feito):

```bash
git clone https://github.com/seu-usuario/seu-repositorio.git
cd seu-repositorio
```

2. Instale as dependências do projeto:

```bash
npm install
# ou
yarn
```

3. Instale o Cypress:

```bash
npm install cypress --save-dev
# ou
yarn add cypress --dev
```

---

## 📂 Estrutura Padrão

```
cypress/
├── e2e/             # Aqui ficam os arquivos de teste
│   └── exemplo.cy.js
├── fixtures/        # Dados estáticos para os testes
├── support/         # Configurações globais e comandos customizados
cypress.config.js    # Arquivo de configuração do Cypress
```

---

## 🧪 Executando os Testes

### ✅ Abrir o Cypress em modo interativo (GUI):

```bash
npx cypress open
```

> Isso abrirá a interface gráfica do Cypress, onde é possível clicar para rodar os testes.

### ⚙️ Executar em modo headless (terminal):

```bash
npx cypress run
```

> Útil para integrar com pipelines CI/CD.

---

## ✍️ Criando um novo teste

Crie um novo arquivo em `cypress/e2e/`, por exemplo:

```bash
touch cypress/e2e/login.cy.js
```

E escreva seu teste usando a API do Cypress:

```js
describe('Página de Login', () => {
  it('deve realizar login com sucesso', () => {
    cy.visit('http://localhost:3000/login')
    cy.get('input[name="email"]').type('usuario@exemplo.com')
    cy.get('input[name="senha"]').type('123456')
    cy.get('button[type="submit"]').click()
    cy.url().should('include', '/dashboard')
  })
})
```

---

## 🛠 Dicas úteis

- Use `cy.intercept()` para simular respostas da API.
- Use `cy.fixture()` para carregar dados estáticos.
- Utilize comandos customizados em `cypress/support/commands.js`.

---

## 📚 Referências

- [Documentação oficial do Cypress](https://docs.cypress.io/)
- [Boas práticas com Cypress](https://docs.cypress.io/guides/references/best-practices)
