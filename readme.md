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








#### 7. Serviços de foundation

## Seção 4: Operação

#### 8. DevOps

#### 9. Estratégias de deploy








