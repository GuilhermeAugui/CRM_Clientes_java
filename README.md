# CRM_Clientes_java

Sistema de CRM desenvolvido em Java para gerenciamento de campanhas de comunicação, segmentação de público-alvo por status do cliente e envio de mensagens, com interface gráfica em Swing e persistência via JDBC.

Projeto acadêmico desenvolvido durante o curso de Análise e Desenvolvimento de Sistemas (UNISINOS), aplicando conceitos de arquitetura em camadas e boas práticas de organização de código.

## Funcionalidades

- Criação e listagem de campanhas de comunicação (nome, data de início e fim)
- Controle de status e progresso da campanha (ex: "Em Execução", "Encerrada")
- Segmentação de clientes por **status de pessoa**, usado como público-alvo das campanhas
- Associação de um ou mais status de pessoa a uma campanha (público-alvo)
- Envio de mensagens vinculadas a uma campanha para os clientes segmentados
- CRUD completo de status de pessoa (criar, listar, atualizar, excluir)
- Interface gráfica em Swing para visualização de campanhas e status cadastrados
- Persistência de dados via banco de dados relacional (JDBC)

## Tecnologias utilizadas

- **Java**
- **Swing** (interface gráfica — `JFrame`, `JList`)
- **JDBC** (conexão com banco de dados via `java.sql.Connection` / `PreparedStatement`)
- Arquitetura em camadas (DAO, DTO, Model, View, Controladora)

## Estrutura do projeto

```
├── controladorora/  # Camada de controle — orquestra as regras de negócio (CampanhaControladora)
├── dao/             # Acesso a dados (CampanhaDAO, StatusPessoaDAO, MensagemDAO)
├── dto/             # Objetos de transferência de dados (CampanhaDTO, StatusPessoaDTO)
├── modelo/          # Entidades do domínio (Campanha, StatusPessoa, Mensagem)
└── visao/           # Interface gráfica (CampanhaView, StatusPessoaView)
```

## Arquitetura

O projeto combina os padrões **DAO/DTO** com uma separação inspirada em **MVC**:
- **Modelo**: entidades de domínio como `Campanha` (com a classe interna `Mensagem`) e `StatusPessoa`
- **DTO**: `CampanhaDTO` e `StatusPessoaDTO` transportam dados entre as camadas
- **DAO**: `CampanhaDAO`, `StatusPessoaDAO` e `MensagemDAO` fazem a comunicação com o banco via JDBC
- **Controladora**: `CampanhaControladora` recebe as ações (criar campanha, definir público-alvo, iniciar/encerrar campanha, enviar mensagens) e coordena DAO e Modelo
- **Visão**: `CampanhaView` e `StatusPessoaView` exibem os dados em janelas Swing

## Como executar

1. Clone o repositório:
   ```bash
   git clone https://github.com/SEU-USUARIO/CRM_Clientes_java.git
   ```
2. Importe o projeto em uma IDE Java (Eclipse, IntelliJ ou NetBeans)
3. Configure a conexão com o banco de dados no arquivo de conexão
4. Execute a classe principal do projeto

## Autor

**Guilherme Augusto Werlang**
Estudante de Análise e Desenvolvimento de Sistemas — UNISINOS
