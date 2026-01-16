# 📊 Despesas Service

## Descrição

O **Despesas Service** é responsável por gerenciar e controlar as despesas pessoais do usuário, incluindo categorização, orçamento e análise de gastos.

**Porta:** `3003`

## ⚙️ Responsabilidades

- 📝 **Registro de Despesas** - Criação e gerenciamento de despesas
- 💰 **Categorização** - Organização por categorias
- 📊 **Orçamento** - Definição e controle de orçamentos
- 📈 **Análise** - Relatórios e insights sobre gastos
- 🎯 **Metas** - Acompanhamento de metas de economia

## 🚀 Endpoints Principais

```bash
GET    /                      # Info da service
GET    /despesas              # Listar despesas
POST   /despesas              # Criar despesa
GET    /despesas/:id          # Detalhes da despesa
PATCH  /despesas/:id          # Atualizar despesa
DELETE /despesas/:id          # Deletar despesa
GET    /despesas/categoria/:cat # Despesas por categoria
GET    /resumo                # Resumo de gastos
GET    /orcamento             # Info de orçamento
POST   /orcamento             # Definir orçamento
```

## 📊 Modelo de Despesa

```typescript
{
  id: string
  user_id: string
  descricao: string
  valor: number
  categoria: string           // Alimentação, Transporte, etc
  data: Date
  mes: string                // YYYY-MM
  status: 'REGISTRADA' | 'PAGA' | 'CANCELADA'
  tags: string[]            // Identificadores customizados
  created_at: Date
  updated_at: Date
}
```

## 🏷️ Categorias Padrão

- 🍔 **Alimentação** - Restaurantes, supermercado
- 🚗 **Transporte** - Combustível, uber, transporte público
- 🏠 **Moradia** - Aluguel, condomínio, energia
- 🏥 **Saúde** - Farmácia, consultas, plano
- 📚 **Educação** - Cursos, livros, mensalidade
- 🎮 **Lazer** - Cinema, games, viagens
- 💼 **Trabalho** - Materiais de trabalho
- 🛍️ **Compras** - Roupas, móveis, eletrônicos
- 📱 **Assinaturas** - Netflix, Spotify, etc
- ❌ **Outros** - Despesas diversas

## 🛠️ Tecnologias

- **NestJS** 10+
- **TypeScript** 5+
- **Prisma** 5+ (ORM)
- **PostgreSQL** / **SQLite** (Database)

## 🚀 Instalação

```bash
cd despesas-service
npm install
```

## ⚙️ Configuração

Crie um arquivo `.env`:

```env
DATABASE_URL=postgresql://user:password@localhost:5432/despesas
# ou
DATABASE_URL=file:./dev.db

PORT=3003
```

## 📦 Rodar a Service

```bash
# Modo desenvolvimento
npm run start:dev

# Modo produção
npm run build
npm run start:prod
```

## 🔄 Prisma

```bash
# Criar/atualizar banco de dados
npx prisma migrate dev

# Gerar tipos TypeScript
npx prisma generate

# Acessar banco via Prisma Studio
npx prisma studio
```

## 📁 Estrutura

```
src/
├── controller/
├── business/           # Lógica de negócio
├── model/             # Tipos e interfaces
├── app.module.ts
└── main.ts
```

## 📈 Exemplo de Resposta

### GET /resumo
```json
{
  "periodo": "2026-01",
  "totalGasto": 2500.00,
  "orcamento": 3000.00,
  "percentualUsado": 83.33,
  "categorias": {
    "Alimentação": 800.00,
    "Transporte": 400.00,
    "Moradia": 1000.00,
    "Outros": 300.00
  },
  "comparacaoMesAnterior": {
    "diferenca": 150.00,
    "percentual": 6.4
  }
}
```

## 🧪 Testes

```bash
npm run test            # Testes unitários
npm run test:watch     # Testes com observer
npm run test:cov       # Cobertura de testes
npm run test:e2e       # Testes E2E
```

## 🔐 Segurança

- ✅ Validação de entrada
- ✅ Dados isolados por usuário
- ✅ JWT em todas as rotas
- ✅ Prepared statements (Prisma)

## 🚀 Próximos Passos

- [ ] Alertas de overspend
- [ ] Previsões de gastos
- [ ] Análise com IA
- [ ] Recomendações de economia
- [ ] Exportação em PDF/CSV

---

**Desenvolvido com ❤️**  
**Última atualização:** 16 de janeiro de 2026
$ npm install
```

## Compile and run the project

```bash
# development
$ npm run start

# watch mode
$ npm run start:dev

# production mode
$ npm run start:prod
```

## Run tests

```bash
# unit tests
$ npm run test

# e2e tests
$ npm run test:e2e

# test coverage
$ npm run test:cov
```

## Deployment

When you're ready to deploy your NestJS application to production, there are some key steps you can take to ensure it runs as efficiently as possible. Check out the [deployment documentation](https://docs.nestjs.com/deployment) for more information.

If you are looking for a cloud-based platform to deploy your NestJS application, check out [Mau](https://mau.nestjs.com), our official platform for deploying NestJS applications on AWS. Mau makes deployment straightforward and fast, requiring just a few simple steps:

```bash
$ npm install -g @nestjs/mau
$ mau deploy
```

With Mau, you can deploy your application in just a few clicks, allowing you to focus on building features rather than managing infrastructure.

## Resources

Check out a few resources that may come in handy when working with NestJS:

- Visit the [NestJS Documentation](https://docs.nestjs.com) to learn more about the framework.
- For questions and support, please visit our [Discord channel](https://discord.gg/G7Qnnhy).
- To dive deeper and get more hands-on experience, check out our official video [courses](https://courses.nestjs.com/).
- Deploy your application to AWS with the help of [NestJS Mau](https://mau.nestjs.com) in just a few clicks.
- Visualize your application graph and interact with the NestJS application in real-time using [NestJS Devtools](https://devtools.nestjs.com).
- Need help with your project (part-time to full-time)? Check out our official [enterprise support](https://enterprise.nestjs.com).
- To stay in the loop and get updates, follow us on [X](https://x.com/nestframework) and [LinkedIn](https://linkedin.com/company/nestjs).
- Looking for a job, or have a job to offer? Check out our official [Jobs board](https://jobs.nestjs.com).

## Support

Nest is an MIT-licensed open source project. It can grow thanks to the sponsors and support by the amazing backers. If you'd like to join them, please [read more here](https://docs.nestjs.com/support).

## Stay in touch

- Author - [Kamil Myśliwiec](https://twitter.com/kammysliwiec)
- Website - [https://nestjs.com](https://nestjs.com/)
- Twitter - [@nestframework](https://twitter.com/nestframework)

## License

Nest is [MIT licensed](https://github.com/nestjs/nest/blob/master/LICENSE).
