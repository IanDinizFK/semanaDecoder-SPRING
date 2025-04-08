# 📚 Semana Decoder - Microsserviços com Spring  
**Estudo de caso: Sistema EAD**  
Este repositório contém anotações e resumos da **Semana Decoder**, com foco em arquitetura de **Microsserviços usando o ecossistema Spring**.

---

## 🎥 Aula 01 — Introdução aos Microsserviços  
> 🎬 **Link da Aula:** _[Fique por dentro!](https://drive.google.com/file/d/160hEjRqJ4SpEn2wWTF-T-ixG8qv-vlUi/view?usp=sharing)_

---

### 💡 Conceitos e Evolução Arquitetural  
> ⏱️ **(2min40s)**  

#### 🔹 Evolução 1 — Sistema Monolítico  
- Frontend + Backend juntos  
- Regras de negócio acopladas  
- Uma única base de dados  

#### 🔹 Evolução 2 — Separação de Frontend e Backend  
- Frontend separado do Backend  
- Backend ainda permanece monolítico  

#### 🔹 Evolução 3 — Arquitetura de Microsserviços  
- Backend dividido em múltiplos serviços independentes  
- Cada serviço possui suas responsabilidades e base de dados própria  

#### 🔹 Evolução 4 — Microsserviços também no Frontend  
- Frontend modularizado em múltiplas aplicações  
- Cada módulo atrelado a um contexto específico  

> Essa evolução proporciona **flexibilidade, escalabilidade e independência** no desenvolvimento de sistemas modernos.

---

### ✅ Benefícios da Arquitetura de Microsserviços  
> ⏱️ **(6min30s)**

- ✅ Manutenibilidade  
- ✅ Alta disponibilidade  
- ✅ Flexibilidade tecnológica  
- ✅ Independência entre equipes  
- ✅ Melhor performance  
- ✅ Divisão da complexidade  
- ✅ Isolamento de falhas  
- ✅ Alta escalabilidade  
- ✅ Baixo acoplamento  
- ✅ Melhor testabilidade  
- ✅ Agilidade nas mudanças  
- ✅ Isolamento na modelagem de dados  
- ✅ Maior resiliência  

---

### 🧠 Microsserviços de Negócio: Definição e Boas Práticas  
> ⏱️ **(10min)**

#### 📌 Compreendendo o Domínio  
Domínios principais no sistema EAD:  
- 👥 **Usuários** (Alunos e Funcionários)  
- 📚 **Cursos**  
- 🔔 **Notificações**  
- 💳 **Pagamentos**  

#### 🔧 Serviços Sugeridos  
- `UserService`  
- `CourseService`  
- `NotificationService`  
- `PaymentService`  

---

### 🎯 Granularidade dos Serviços  
> ⏱️ **(13min30s)**

#### ❌ Mini-monólitos  
- Muitos recursos e responsabilidades juntos  
- Alto acoplamento  

#### ❌ Nano-serviços  
- Serviços pequenos demais  
- Excesso de comunicação  

#### ✅ Quando dividir um serviço?  
- Quando há muitas responsabilidades ou alto acoplamento  

##### Exemplo prático:  
- `NotificationService` → `GmailSMTPService`, `AWSSMTPService`, `SMSService`  
- `PaymentService` → `PagSeguroService`, `PayPalService`  

> Melhora a manutenibilidade e resiliência.

---

### ⚠️ Cuidado com a Fragmentação Excessiva  
> ⏱️ **(16min)**

- Aumento do tráfego entre serviços  
- Complexidade de manutenção  
- Integração difícil  

---

## 🌐 Ecossistema Spring e Infraestrutura  

### 🚀 Usando o Ecossistema Spring  
> ⏱️ **(17min40s)**  

- `Spring Boot` – Inicialização rápida  
- `Spring Security` – Segurança  
- `Spring Cloud` – Arquitetura distribuída  
- `Spring Data` – Integração com bases de dados  
- `Spring Web`, `Spring AMQP`, `Spring Batch`  

Permite trabalhar com:  
- Cloud-native  
- Programação reativa  
- Batch e Event-driven  
- Diversas tecnologias de banco de dados  

---

### 🛢️ Estratégia de Base de Dados  
> ⏱️ **(24min a 26min)**  

#### ❌ Base Compartilhada  
- Forte consistência, mas alto acoplamento  

#### ✅ Base por Microsserviço  
- Flexibilidade tecnológica  
- Independência para escalar  
- Isolamento de falhas  

Tecnologias compatíveis com Spring Data:  
- JPA  
- MongoDB  
- Redis  

---

### 📌 Identificadores Universais (UUID)  
> ⏱️ **(28min)**  

- Evitam colisões de ID em ambientes distribuídos  
- IDs sequenciais não são seguros em microsserviços  

---

### 🔗 Comunicação entre Microsserviços  
> ⏱️ **(30min)**  

- Desacoplamento **absoluto é mito**  
- Algum grau de acoplamento é sempre necessário  

---

### ⚙️ Microsserviços de Configuração  
> ⏱️ **(33min)**  

- Serviços que tratam de **preocupações transversais**  
- Não contêm regras de negócio  

---

### 🌉 API Gateway  
> ⏱️ **(34min30s a 37min40s)**  

#### O que é:  
- Porta única para requisições externas  
- Roteia requisições para os microsserviços  

#### Ferramenta:  
- `Spring Cloud Gateway`  
  - Baseado em Project Reactor  
  - Programação reativa com Netty  
  - Permite filtros, predicados, controle de tráfego, integração com Service Registry  

---

### 📘 Service Registry  
> ⏱️ **(42min a 44min10s)**  

- Gerencia registro e descoberta de instâncias  
- Fornece IP, porta e domínio aos serviços  

#### Ferramentas:  
- `Spring Cloud Netflix Eureka`  
- Alternativa: `Spring Cloud LoadBalancer`  

---

### 🛠️ Global Configuration  
> ⏱️ **(46min a 49min)**  

#### Problema:  
- Muitos arquivos `.properties` dispersos  
- Difícil versionamento e manutenção  

#### Solução:  
- `Spring Cloud Config`  
  - Centraliza configurações  
  - Integração com Git  
  - API REST  
  - Suporte a criptografia  
  - Recarregamento com `@RefreshScope`  

---

### 🔎 Padrões de Observabilidade  
> *(Em breve)*  

Ferramentas previstas:  
- `Spring Boot Actuator`  
- `Zipkin`  
- `ELK`  
- `Prometheus`  
- `Grafana`  

---

## ✅ Conclusão  
A arquitetura de microsserviços eficiente nasce de um entendimento claro do negócio. Boas práticas incluem:

- Coesão  
- Baixo acoplamento  
- Independência  
- Alinhamento com o domínio da aplicação  

---

## 🛠 Tecnologias Utilizadas  

- Java 17+  
- Spring Boot  
- Spring Cloud *(futuro)*  
- Maven  
- Docker *(futuro)*  
