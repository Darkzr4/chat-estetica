# **Documentação — EsteticaBot**

| Meta de Lançamento | 07 de abril de 2025 |
| --- | --- |
| Épico | Desenvolver um chatbot baseado em IA para clínicas estéticas, utilizando Python e Amazon Bedrock, para fornecer informações sobre serviços, agendamentos e notificações automatizadas. |
| Status do documento | Em andamento |
| Equipe de desenvolvedores |  |
| Scrum Master | Jefferson Cavalcante Vieira |
| Arquitetos |  |

## 🎯 Objetivo

Este projeto tem como finalidade desenvolver uma solução inovadora de Inteligência Artificial utilizando a linguagem de programação Python, integrando um modelo de linguagem fornecido pelo Amazon Bedrock, com o objetivo de criar um chatbot interativo e altamente eficiente para assistência em clínicas estéticas.

## 📊 Indicadores de Sucesso

### **Indicadores de Sucesso**

O chatbot deve ser capaz de:

- Atender clientes da clínica estética com informações sobre serviços, preços e horários disponíveis.
- Permitir agendamentos automáticos de consultas.
- Enviar notificações para confirmação e lembrete de atendimentos.
- Responder de forma natural e personalizada utilizando IA generativa do Amazon Bedrock.
- Garantir um tempo de resposta rápido e uma interface intuitiva.

## 📜 Premissas

- O sistema será baseado em uma arquitetura serverless, garantindo escalabilidade e eficiência.
- Tecnologias AWS serão utilizadas para integração, segurança e armazenamento de dados.
- O desenvolvimento seguirá boas práticas de segurança, incluindo controle de acesso via IAM.
- A solução será responsiva e acessível por dispositivos móveis e desktop.

## 📑 Requisitos

### **Requisitos Funcionais**

**Desenvolvimento Back-end**:

- Implementação do serviço utilizando a linguagem Python e boto3.

**Integração com Serviços AWS**:

- Utilização do Amazon S3 para armazenamento e do Amazon Bedrock (Claude 3.5 Sonnet v2) para geração de respostas inteligentes.
- Uso do Amazon Lex para criação da interface de conversação do chatbot.
- Utilização do DynamoDB para armazenar informações dos clientes e agendamentos.
- Notificações automatizadas via Amazon SNS.

**Armazenamento e Segurança**:

- Garantia de armazenamento seguro dos dados no DynamoDB e S3.
- Controle de acesso configurado via AWS IAM.

### **Requisitos Não Funcionais**

**Desempenho**:

- O chatbot deve garantir alta responsividade, oferecendo tempos de resposta inferiores a 5 segundos.

**Linguagem utilizada e Bibliotecas:**

- O desenvolvimento será realizado utilizando a linguagem Python com boto3 para interação com AWS.

**Integração com Serviço de Inteligência Artificial**:

- O sistema utilizará o Amazon Bedrock para processar e gerar respostas personalizadas, com base na documentação disponibilizada.

## 📖 Histórias de Usuário

***R1 → Como cliente, quero poder perguntar sobre os serviços disponíveis na clínica para que eu possa entender quais são adequados para mim.***

- **Critérios de aceite:**
    - O chatbot deve responder de forma natural e precisa sobre os serviços oferecidos.
    - O sistema deve estar integrado ao Amazon Bedrock para respostas personalizadas.

***R2 → Como cliente, quero poder agendar um serviço diretamente pelo chatbot para facilitar meu atendimento.***

- **Critérios de aceite:**
    - O chatbot deve validar a disponibilidade de horários no DynamoDB.
    - O sistema deve registrar o agendamento e enviar uma confirmação via SNS.

***R3 → Como cliente, quero receber lembretes do meu agendamento para evitar atrasos ou esquecimentos.***

- **Critérios de aceite:**
    - O chatbot deve enviar um lembrete via Amazon SNS um dia antes do agendamento.

## 🧑‍💻🛠️ Tecnologias & Ferramentas

### Serviços Utilizados e suas Funcionalidades

- **IAM:** Garante a segurança da aplicação, controlando quem acessa quais recursos da AWS e com quais permissões.
- **Route 53:** Direciona o tráfego de internet para a aplicação, atuando como um DNS inteligente, otimizando a rota para o usuário.
- **CloudFront:** Acelera a entrega de conteúdo estático da aplicação, como imagens e scripts, para os usuários, melhorando a performance.
- **Lex:** Permite criar interfaces de chatbot, para interagir com os usuários de forma natural e intuitiva.
- **DynamoDB:** Armazena dados de forma flexível e escalável, para armazenar informações dos usuários e agendamentos.
- **Bedrock (Claude 3.5 Sonnet v2)**: IA generativa para processamento e geração de respostas personalizadas.
- **Lambda:** Orquestração do fluxo de interação entre Lex, Bedrock e DynamoDB.

## 📌 Backlog | Melhorias

- Aprimorar a precisão do chatbot na resposta a perguntas complexas.
- Otimizar o tempo de resposta para menos de 3 segundos.
- Implementar suporte a múltiplos idiomas.
- Adicionar análise de interação dos usuários para melhoria contínua do chatbot.
- Adicionar método de pagamento integrado, utilizando o AWS API Gateway, integrando o Amazon Pay.

