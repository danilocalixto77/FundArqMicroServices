# Fundamentos de Arquitetura de Microsservições (Microservices)
***Eduardo Felipe Gomes***

## Seção 1: Introdução

#### 1. Porque microssserviços?

Palavras chaves:

- Por que usar microserviços:
- Monolíto
- Distribuídos
- Arquitetura de microssserviços
- Custo 
- Escalabilidade
- Desempenho
- Compartilhamento

Delimitando:

- **Domain-Driven Design**: Atacando a **complexidade** do software através de **modelos**.


## Seção 2: Arquitetura

#### 2. Escala e distribuição

- Formas de escalar!
- Vertical: adicionando recursos ao serviço.
- Horizontal: adicionando instâncias do serviço.
- Impacto direto no custo! (Autoscaling)

- Escalar database?
- **Database** é o ponto de **sobrecarga** do **serviço**.
- Opções: **escalar vertical** ou criar um **cluster** (caro)?
- **Consultas** exigem **mais recursos**.

CQRS (**Command QUery Responsibility Segregation**)

**Dividindo Responsabilidades**
Comandos divididos de consultas na base de dados.

**Modelos diferentes**

Dependendo da operação, o serviço pode interagir com **modelos diferentes** (modelo de consultas e modelo de comando)


#### 3. Multitenancy

- vários clientes compartilhando o mesmo serviço, ganhando um menor custo.

- Custo!

E o Database?

São três formas:

- **Bancos** separados (nstâncias separadas).

- **Schemas** separados.

- **Particionando** (discriminador).

- **Tenant** ???

#### 4. Integrando Serviços

- Mensagens

- **Serviço** utiliza **publicação** e **subscrições** de **eventos** para comunicação **assícrona**

    Publicar -> Fila -> Assinar

- **REST**

- **Serviço** utiliza camada **HTTP** para integração de forma **síncrona**

    GET | POST | PUT | DELETE

Recomendação utilização de serviços **assincronos** e reservando os **síncronos** para exceções, utilizando com muita cautela.

## Seção 3: Plataforma

#### 5. Visão geral

Framework

Plataforma componente de infraestrutura.

Processo de Desenvolvimento

#### 6. Componentes

**API Manager**
(API Gateway)

- **Ponto único** de acssso a **todas** as **APIs**.

- **Filtragem** de dados e **direcionamento**.

- Integração com **autenticação**.

**Authentication Service** (Autenticação)

- **Identifica** o usuário no **sistema**.

- **Provê infomações** do usuário.

**Authorization Service** (Autorização)

- **Verifica permissõs** do usuário no **sistema**.

- Gerecia papeis e **recursos**.

**Load Balance** (Regulador de carga)

- **Administra** a **carga** de requisições entre as **instâncias** dos **serviços**.

**Servcice Discovery** (Identificação de serviços)

- **Registra** os serviços **disponíveis**.

- **Centraliza** a informação de **serviços** X **instâncias** (IPs).

**Service Config** (Configurações dos serviços)

**Centraliza** configurações dos **serviços**:

- **Conexões de bancos de dados**.
- **Certificados públicos**.


**Monitoring & Alert** (Monitoramento e Alertas)

- Prove **dados** em **tempo real**.
- Utiliza **endpoints** de health check.
- **Processa** e **refina** informações de log.
- Apresenta as **informações** em **dashboards**.

**Container Orchestration** (Orquestração de containers)

- **Gerencia** as **instâncias** dos serviços.
- Faz o **autoscaling** e **downscaling**.

**Message Broker** (Mensageria)

- **Centraliza o recebimento** e **sinalização de eventos**.
- **Gerencia as filas** e **entregas de mensagens**.

**Storage** (Armazenamento)

- Serviço para **armazenamento** de arquivos como imagens, vídeos e documentos.

#### 7. Serviços de foundation

Serviços básicos:

-- Envio de e-mail, SMS, WA

- Agendamente de tarefas (JOB)

- Relatórios

## Seção 4: Operação

#### 8. DevOps

Ciclo DevOps:

    Plain -> Code -> Build -> Test -> Deploy -> Integrate -> Operate -> Monitoramento

E após conclusão do clico ele ser reiniciar passando por acada etapa novamente.

CI - Continuos Integration

    Build [Auto]-> Unit Test [Auto]-> Deploy Stage [Aauto]-> Acceptance Tests 

CD - Continuous Delivery

    Build [Auto]-> Unit Test [Auto]-> Deploy Stage [Aauto]-> Acceptance Tests [Manual] -> Deploy Production

CD - Continuous Deployment

    Build [Auto]-> Unit Test [Auto]-> Deploy Stage [Aauto]-> Acceptance Tests [Auto] -> Deploy Production

#### 9. Estratégias de deploy

Blue / Green

Canary

Expansão e contração:

- Início: Implementa a refatoração **[Expansão]**
- Trnsição: Período de transição do velho para o novo
- Fim: Refatoração completa **[Contração]**











