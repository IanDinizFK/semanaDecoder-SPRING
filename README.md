# 📚 Semana Decoder - Microsserviços com Spring
## Case: Sistema EAD
Este repositório contém os estudos e anotações da **Semana Decoder**, com foco na arquitetura de **Microsserviços utilizando Spring Framework**.

---

## 📅 Dia 01 - Introdução aos Microsserviços (Anotações)

### 💡 Aula teórica: Conceitos e Evolução Arquitetural

#### 🔹 Evolução 1 - Sistema Monolítico (2min40s)
Aplicações construídas como um único bloco contendo:
- Frontend + Backend juntos;
- Todas as regras de negócio fortemente acopladas;
- Uso de uma única base de dados.

#### 🔹 Evolução 2 - Separação de Frontend e Backend
- Frontend separado do Backend;
- Backend ainda permanece monolítico.

#### 🔹 Evolução 3 - Arquitetura de Microsserviços
- Backend dividido em **múltiplos serviços independentes**;
- Cada serviço possui responsabilidades e funcionalidades específicas;
- Serviços funcionam de forma autônoma;
- Cada um pode utilizar sua **própria base de dados**.

#### 🔹 Evolução 4 - Microsserviços também no Frontend
- Frontend também passa a ser modularizado em múltiplas aplicações;
- Cada módulo é associado a um serviço ou contexto específico.

> Essa evolução atende à necessidade de **flexibilidade, escalabilidade e independência** no desenvolvimento de sistemas modernos.

---

## ✅ Benefícios da Arquitetura de Microsserviços (6min30s)

- ✅ Manutenibilidade
- ✅ Alta disponibilidade
- ✅ Flexibilidade tecnológica
- ✅ Independência entre equipes
- ✅ Melhor performance
- ✅ Divisão da complexidade do negócio
- ✅ Isolamento de falhas
- ✅ Alta escalabilidade
- ✅ Baixo acoplamento
- ✅ Melhor testabilidade
- ✅ Agilidade nas mudanças
- ✅ Isolamento na modelagem de dados
- ✅ Maior resiliência

---
## 🧠 Microsserviços de Negócio - Definição e Boas Práticas 10min

Ao projetar uma arquitetura baseada em microsserviços, o primeiro passo é definir claramente os **Microsserviços de Negócio**, com base em uma análise profunda das funcionalidades e regras da aplicação.

### 📌 Compreendendo o Domínio

No contexto de um sistema EAD (Ensino a Distância), devemos identificar:

- As **ações** do sistema;
- As **funcionalidades** envolvidas;
- Os **domínios** principais;
- As **regras de negócio**.

Exemplos de domínios identificados:
- 👥 **Usuários** (Alunos e Funcionários)
- 📚 **Cursos**
- 🔔 **Notificações**
- 💳 **Pagamentos**

### 🔧 Serviços sugeridos

Com base nos domínios acima, podemos estruturar os seguintes serviços:

- `UserService`
- `CourseService`
- `NotificationService`
- `PaymentService`

---

## 🎯 Granularidade dos Serviços 13min30s

A definição da granularidade ideal depende das necessidades do projeto. No entanto, é importante evitar dois extremos:

### ❌ Mini-monólitos
- Serviços grandes demais, com muitas responsabilidades.
- Regras de negócio misturadas e alto acoplamento.

### ❌ Nano-serviços
- Serviços pequenos demais, com funcionalidades rasas.
- Excesso de comunicação entre serviços.

---

## 🧩 Quando dividir um serviço?

A divisão de um serviço deve acontecer quando ele apresentar:
- Muitas responsabilidades;
- Complexidade crescente;
- Alto acoplamento interno.

### ✅ Exemplo prático

Dividindo o `NotificationService`:
- `GmailSMTPService`
- `AWSSMTPService`
- `SMSService`

Dividindo o `PaymentService`:
- `PagSeguroService`
- `PayPalService`

> Com essa abordagem, melhoramos a manutenibilidade e a resiliência, permitindo isolar e resolver falhas com mais facilidade.

---

## ⚠️ Cuidado com a fragmentação excessiva

Dividir demais pode gerar **problemas de arquitetura**:
- Aumento do tráfego de comunicação entre serviços;
- Dificuldade de manutenção;
- Maior complexidade na integração.

---

## ✅ Conclusão

A melhor arquitetura de microsserviços nasce de um entendimento sólido do negócio. O objetivo é criar serviços:
- Coesos;
- Pouco acoplados;
- Independentes;
- E alinhados com os domínios reais da aplicação.

## 🛠 Tecnologias utilizadas

- Java 17+
- Spring Boot
- Spring Cloud (em aulas futuras)
- Maven
- Docker (em aulas futuras)

---

## 📁 Estrutura do Repositório

