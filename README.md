# VixLegen

> Sistema de gerenciamento e assistência jurídica com foco em organização de processos, controle de prazos, edição de documentos e apoio por Inteligência Artificial.

**Status:** Em desenvolvimento — projeto acadêmico do curso Técnico em Desenvolvimento de Sistemas da Escola SENAI “Anchieta”.

## Sobre o projeto

O **VixLegen** foi idealizado para auxiliar advogados, escritórios de advocacia e departamentos jurídicos na rotina de trabalho. A proposta reúne em um único ambiente recursos para edição de peças jurídicas, acompanhamento de tarefas, controle de prazos, notificações, gerenciamento de processos e suporte de Inteligência Artificial.

A IA é planejada como uma **ferramenta de apoio ao profissional**, e não como substituta do advogado ou mecanismo autônomo de tomada de decisões. O projeto prevê o uso de **RAG (Retrieval-Augmented Generation)** para fornecer contexto jurídico ao modelo e reduzir respostas sem fundamento.

## Objetivos

- Reduzir o tempo gasto na leitura e elaboração de documentos jurídicos.
- Organizar processos, tarefas e atividades do escritório.
- Ajudar no acompanhamento de prazos e reduzir o risco de perda de datas importantes.
- Disponibilizar um editor de documentos voltado ao contexto jurídico.
- Utilizar IA para auxiliar em leitura, escrita, revisão, resumos e análises processuais.
- Centralizar informações de clientes, processos, documentos, movimentações e notificações.

## Funcionalidades

### Protótipo Front-end atual

O protótipo disponível atualmente possui:

- **Editor jurídico WYSIWYG** com:
  - negrito, itálico, sublinhado e tachado;
  - alinhamento de texto;
  - listas;
  - seleção de fonte, tamanho e cor;
  - espaçamento entre linhas;
  - citação jurídica com recuo;
  - inserção de nota de rodapé;
  - inserção de links;
  - modelos de Petição Inicial, Contestação e Procuração;
  - contador de palavras e caracteres;
  - ação de exportação para PDF pelo recurso de impressão do navegador.
- **Quadro Kanban** com colunas de tarefas e criação de novos cartões.
- **Central de notificações** com filtros e controle de itens lidos/não lidos.
- **Área da empresa** com visualização e edição de dados cadastrais.
- **Perfil profissional** do usuário.
- **Área de Assistente Jurídico IA** preparada na interface.
- Navegação em formato **Single Page Application (SPA)** no protótipo.

### Funcionalidades previstas para o sistema completo

- Cadastro e autenticação de usuários.
- Gestão de clientes.
- Gestão de processos jurídicos.
- Controle de partes envolvidas e classificação processual.
- Gerenciamento de documentos jurídicos.
- Controle de tarefas e responsáveis.
- Registro de movimentações processuais.
- Notificações de prazos e acontecimentos importantes.
- Relatórios e consultas de processos.
- Integração de IA para análise processual e geração de apoio textual.
- Evolução futura para integrações com serviços e sistemas jurídicos externos.

## Tecnologias

### Protótipo Front-end atual

- HTML5
- CSS3
- JavaScript
- Font Awesome
- Google Fonts

### Arquitetura planejada para a aplicação completa

**Back-end**

- Java 21
- Spring Boot 3.x
- Spring Web
- Spring Data JPA
- Hibernate
- Spring Validation
- Spring Security / JWT
- Lombok
- Maven

**Banco de dados**

- MySQL 8

**Front-end planejado**

- React

**Módulo de Inteligência Artificial**

- Python
- Arquitetura RAG
- Bibliotecas de IA/NLP conforme evolução do projeto

**Ferramentas de desenvolvimento**

- IntelliJ IDEA
- Visual Studio Code
- MySQL Workbench
- Postman
- Git / GitHub
- Canva
- Notion

## Arquitetura

O back-end foi planejado seguindo uma **arquitetura em camadas**, separando responsabilidades para facilitar manutenção, testes e evolução do sistema.

```text
Controller
    ↓
Service
    ↓
Repository
    ↓
Banco de Dados (MySQL)
```

Estrutura prevista:

```text
src/
├── controller/
├── service/
├── repository/
├── model/
├── dto/
├── exception/
├── config/
├── security/
└── util/
```

### Responsabilidades

- **Controller:** recebe as requisições e disponibiliza as APIs REST.
- **Service:** concentra regras de negócio e validações.
- **Repository:** realiza o acesso aos dados utilizando Spring Data JPA.
- **Model/Entity:** representa as entidades persistidas no banco.
- **DTO:** transporta dados entre as camadas e a API.
- **Security:** concentra autenticação e autorização.
- **Exception:** centraliza o tratamento de erros da aplicação.

## Principais entidades

A modelagem do sistema inclui entidades como:

- Categoria
- Usuário
- Cliente
- Processo Jurídico
- Parte Envolvida
- Classificação do Processo
- Categoria de Documento
- Documento Jurídico
- Colaborador
- Tarefa
- Notificação
- Movimentação Processual
- Análise de Inteligência Artificial

## Banco de dados

O projeto possui modelagem relacional em **MySQL**, com tabelas e relacionamentos para usuários, clientes, processos, documentos, tarefas, notificações, movimentações e análises de IA.

Exemplo simplificado do fluxo de relacionamento:

```text
Categoria 1 ───── N Usuário
Usuário   1 ───── N Tarefa
Usuário   1 ───── N Notificação
Cliente   1 ───── N Processo Jurídico
Processo  1 ───── N Documento Jurídico
Processo  1 ───── N Tarefa
Processo  1 ───── N Movimentação Processual
Processo  1 ───── N Análise IA
```

## API REST planejada

Alguns endpoints definidos na documentação do projeto:

```http
GET    /usuarios
POST   /usuarios
PUT    /usuarios/{id}
DELETE /usuarios/{id}

GET    /clientes
POST   /clientes
PUT    /clientes/{id}
DELETE /clientes/{id}

GET    /processos
GET    /processos/{id}
POST   /processos
PUT    /processos/{id}
DELETE /processos/{id}

GET    /tarefas
POST   /tarefas
PUT    /tarefas/{id}
DELETE /tarefas/{id}

GET    /notificacoes
POST   /notificacoes
```

## Como executar o protótipo Front-end

### Opção 1 — Abrir diretamente

1. Baixe ou clone o projeto.
2. Mantenha `index.html`, `style.css` e `script.js` na mesma pasta.
3. Abra o arquivo `index.html` em um navegador moderno.

### Opção 2 — Live Server

No Visual Studio Code:

1. Instale a extensão **Live Server**.
2. Abra a pasta do projeto.
3. Clique com o botão direito em `index.html`.
4. Selecione **Open with Live Server**.

> O protótipo utiliza recursos externos via CDN, portanto algumas fontes e ícones dependem de conexão com a internet.

## Estrutura atual do Front-end

```text
VixLegen/
├── index.html      # Estrutura e telas da aplicação
├── style.css       # Layout, componentes e responsividade
├── script.js       # Navegação e interações do protótipo
└── README.md
```

A documentação acadêmica do projeto também inclui arquivos de requisitos, visão, metodologia, arquitetura, implementação, modelagem de classes, banco de dados e planejamento de sprints.

## Metodologia

O projeto utiliza práticas de desenvolvimento ágil, com **Kanban** para visualização do fluxo de trabalho e organização das tarefas. A documentação também registra o uso de Scrum durante o planejamento da equipe.

## Equipe

| Integrante | Atuação registrada no projeto |
|---|---|
| Marco Antonio D’Alessio | Front-end e Python |
| Yago Souza | Front-end e Banco de Dados |
| Raphael Silva | Back-end, JavaScript e Banco de Dados |
| Willian Gama | Back-end e Mobile |
| Pedro Henrique | Python e Mobile |

**Orientador:** Prof. Tércio Borges Ribeiro.

## Segurança e confiabilidade

Entre os pontos previstos para a evolução do sistema estão:

- autenticação e autorização com JWT;
- validação dos dados de entrada;
- controle de permissões por categoria de usuário;
- prevenção de cadastros duplicados;
- tratamento padronizado de exceções;
- integridade dos dados armazenados;
- estratégias de backup e recuperação.

## Inteligência Artificial

A proposta do módulo de IA é auxiliar o advogado em tarefas como:

- leitura e resumo de processos extensos;
- apoio à elaboração de documentos;
- revisão de conteúdo;
- identificação de informações relevantes;
- sugestões baseadas no contexto disponível.

O VixLegen prevê o uso de **RAG** para recuperar informações de uma base de conhecimento antes da geração da resposta. No protótipo acadêmico, a documentação admite o uso de uma base jurídica simulada quando integrações externas pagas não estiverem disponíveis.

> **Importante:** as respostas da IA devem ter caráter auxiliar e precisam ser revisadas pelo profissional responsável.

## Próximos passos

- Integrar o Front-end com a API Spring Boot.
- Finalizar autenticação e permissões.
- Conectar a aplicação ao MySQL.
- Implementar CRUDs das entidades principais.
- Implementar upload e gerenciamento de documentos.
- Integrar notificações e controle real de prazos.
- Desenvolver o módulo Python/RAG.
- Criar testes unitários e de integração.
- Evoluir a interface para React conforme a arquitetura planejada.
- Avaliar integrações com tribunais, armazenamento em nuvem e canais de notificação.

## Aviso

O VixLegen é um projeto acadêmico em desenvolvimento. Dados, processos, empresas, profissionais e informações jurídicas presentes no protótipo podem ser **fictícios ou utilizados apenas para demonstração**.

---

<p align="center">
  <strong>VixLegen</strong><br>
  Auxílio e praticidade para o trabalho jurídico com tecnologia e Inteligência Artificial.
</p>
