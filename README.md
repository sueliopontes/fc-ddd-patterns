# FC DDD Patterns

Um projeto de exemplo implementando padrões de **Domain-Driven Design (DDD)** em TypeScript, com enfoque em boas práticas de arquitetura limpa e testes automatizados.

## 📋 Descrição

Este projeto demonstra a aplicação dos principais conceitos e padrões DDD, incluindo:

- **Entidades e Value Objects** - Objetos que representam conceitos do domínio
- **Agregados** - Agrupamentos de entidades relacionadas
- **Factories** - Padrão de criação de objetos
- **Repositories** - Abstração para acesso aos dados
- **Event Dispatching** - Sistema de eventos do domínio
- **Services** - Lógica de negócio complexa

## 🏗️ Arquitetura

O projeto está estruturado em camadas:

```
src/
├── domain/           # Lógica de negócio (núcleo da aplicação)
│   ├── @shared/      # Interfaces e utilitários compartilhados
│   ├── checkout/     # Domínio de Pedidos
│   ├── customer/     # Domínio de Clientes
│   └── product/      # Domínio de Produtos
└── infrastructure/   # Implementações de persistência
    ├── customer/     # Repositório de Clientes (Sequelize)
    ├── order/        # Repositório de Pedidos (Sequelize)
    └── product/      # Repositório de Produtos (Sequelize)
```

## 🚀 Pré-requisitos

Antes de começar, certifique-se de ter instalado:

- **Node.js** (v14 ou superior)
- **npm** ou **yarn** (gerenciador de pacotes)

Verifique as versões instaladas:

```bash
node --version
npm --version
```

## 📦 Instalação

1. Clone o repositório:

```bash
git clone <seu-repositorio>
cd fc-ddd-patterns
```

2. Instale as dependências:

```bash
npm install
```

## 🎯 Como Executar

### Compilar TypeScript

Para compilar o código TypeScript para JavaScript:

```bash
npm run tsc
```

### Executar os Testes

Para executar todos os testes:

```bash
npm test
```

Este comando executa:
1. Verificação de tipos com TypeScript (`tsc --noEmit`)
2. Testes com Jest



## 🧪 Testes

O projeto utiliza **Jest** para testes unitários. Os testes estão localizados junto com os respectivos arquivos, com a extensão `.spec.ts`.

### Estrutura dos Testes

```
domain/
├── checkout/
│   ├── entity/
│   │   └── order.spec.ts
│   ├── factory/
│   │   └── order.factory.spec.ts
│   └── service/
│       └── order.service.spec.ts
...
```

### Executar com cobertura de testes

```bash
npx jest --coverage
```

## 📚 Principais Dependências

| Dependência | Versão | Descrição |
|-----------|--------|-----------|
| TypeScript | ^4.5.5 | Linguagem tipada baseada em JavaScript |
| Jest | ^27.5.1 | Framework de testes |
| Sequelize | ^6.37.8 | ORM para banco de dados |
| Sequelize-TypeScript | ^2.1.6 | Tipos para Sequelize |
| SQLite3 | ^5.1.7 | Banco de dados |
| UUID | ^8.3.2 | Geração de IDs únicos |

## 📖 Conceitos DDD Implementados

### Entidades
Objetos com identidade única que percorrem o ciclo de vida da aplicação.
- `Customer` - Representa um cliente
- `Product` - Representa um produto
- `Order` - Representa um pedido

### Value Objects
Objetos que representam valores e não possuem identidade, apenas igualdade baseada em seu conteúdo.
- `Address` - Endereço de um cliente

### Factories
Padrão de criação que encapsula a lógica de construção de objetos complexos.
- `CustomerFactory` - Cria instâncias de clientes
- `ProductFactory` - Cria instâncias de produtos
- `OrderFactory` - Cria instâncias de pedidos

### Repositories
Interfaces que definem como persistir e recuperar agregados.
- `CustomerRepository` - Persistência de clientes
- `ProductRepository` - Persistência de produtos
- `OrderRepository` - Persistência de pedidos

### Event Dispatcher
Sistema para disparar e escutar eventos do domínio.
- `EventDispatcher` - Gerencia eventos
- `EventHandler` - Interface para manipuladores de eventos

### Services
Lógica de negócio que envolve múltiplas entidades.
- `OrderService` - Processar pedidos
- `ProductService` - Gerenciar produtos

## 🔧 Scripts Disponíveis

```json
{
  "test": "npm run tsc -- --noEmit && jest",
  "tsc": "tsc"
}
```

| Script | Comando | Descrição |
|--------|---------|-----------|
| test | `npm test` | Verifica tipos e executa testes |
| compile | `npm run tsc` | Compila TypeScript para JavaScript |


## 📝 Estrutura de Pastas

```
fc-ddd-patterns/
├── src/
│   ├── domain/                    # Lógica de negócio
│   │   ├── @shared/              # Código compartilhado
│   │   ├── checkout/             # Domínio de pedidos
│   │   ├── customer/             # Domínio de clientes
│   │   └── product/              # Domínio de produtos
│   └── infrastructure/           # Implementação técnica
│       ├── customer/
│       ├── order/
│       └── product/
├── jest.config.ts               # Configuração do Jest
├── tsconfig.json                # Configuração do TypeScript
├── tslint.json                  # Configuração do TSLint
├── package.json                 # Dependências do projeto
└── README.md                    # Este arquivo
```