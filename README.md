
# EsteticaBot - Seu Assistente de Beleza
<p align="center"><i>Um chatbot interativo que auxilia no agendamento de serviços de clínicas estéticas. Além de agendar, ele notifica sobre os agendamentos e tira dúvidas sobre os serviços.</i></p>

## 🎯 Objetivo do Projeto

Este projeto tem como finalidade desenvolver uma solução inovadora de Inteligência Artificial utilizando a linguagem de programação Python, integrando um modelo de linguagem fornecido pelo Amazon Bedrock, com o objetivo de criar um chatbot interativo e altamente eficiente para assistência em clínicas estéticas.
## 💎 Proposta de Valor

- **Experiência Personalizada**
Oferecemos serviços totalmente adaptados às necessidades individuais de cada cliente, garantindo que suas expectativas sejam superadas.

 - **Facilidade no Agendamento**
 Processo simplificado e intuitivo para marcar, remarcar ou cancelar serviços, disponível em múltiplos canais.
 
- **Redução de Cancelamentos**
Minimizamos faltas e cancelamentos através de engajamento proativo e políticas flexíveis.
- **Eficiência Operacional**
Ferramentas que otimizam a gestão de recursos, tempo e equipe para aumentar a produtividade.

- **Acessibilidade e Conveniência**
Serviços disponíveis para todos, com opções inclusivas e adaptáveis a diferentes necessidades.

## 🏋️ Habilidades Exercitadas
- **Técnicas:** Python, arquitetura de software, data sourcing e integração com IA.
- **Organizacionais:** Comunicação, colaboração em equipe e gestão de projetos.

## 🛠️ Solução

O EsteticaBot é um chatbot capaz de:
- Atender clientes da clínica estética com informações sobre serviços, preços e horários disponíveis.
- Permitir agendamentos automáticos de consultas.
- Enviar notificações para confirmação e lembrete de atendimentos.
- Responder de forma natural e personalizada utilizando IA generativa do Amazon Bedrock.
- Garantir um tempo de resposta rápido e uma interface intuitiva.



## 🔄 Metodologia Ágil
- Kanban
- Ferramentas utilizadas: [Notion](https://www.notion.so/Documenta-o-EsteticaBot-189bc90f5d0f803893cac65bd6515bf2?pvs=4)



## 📋 Requisitos

### Requisitos Funcionais
- Implementação do serviço utilizando a linguagem Python e boto3.
- Utilização do Amazon Bedrock (Claude 3.5 Sonnet v2) para geração de respostas inteligentes.
- Uso do Amazon Lex para criação da interface de conversação do chatbot.
- Utilização do DynamoDB para armazenar informações dos clientes e agendamentos.
- Notificações automatizadas via Amazon SNS.
- Garantia de armazenamento seguro dos dados no DynamoDB.
- Controle de acesso configurado via AWS IAM.

### Requisitos Não Funcionais
- O chatbot deve garantir alta responsividade, oferecendo tempos de resposta inferiores a 5 segundos.
- O desenvolvimento será realizado utilizando a linguagem Python com boto3 para interação com AWS.
- O sistema utilizará o Amazon Bedrock para processar e gerar respostas personalizadas, com base na documentação disponibilizada.

## ☁️ Arquitetura da AWS


![Fluxograma da arquitetura](https://i.imgur.com/YmGjPF5.png)

## 🛠️ Tecnologias Utilizadas

### **AWS Route 53**  
Registro de domínio do site da clínica e resolução DNS.

### **AWS CloudFront**  
Distribuição global do conteúdo estático/dinâmico do site com baixa latência.

### **Amazon Lex**  
Chatbot para interação com usuários via texto (e voz, se aplicável), processando perguntas como:
- _"Quais serviços a clínica oferece?"_
- _"Qual o preço de um procedimento?"_

### **AWS Lambda (Python + Boto3)**  
Executa funções serverless para:
- Processar solicitações do Lex
- Consultar/atualizar agendamentos no DynamoDB
- Integrar-se ao Bedrock para respostas personalizadas
- Acionar notificações via SNS

### **Amazon DynamoDB**  
Banco de dados NoSQL que armazena:
- Catálogo de serviços e preços
- Horários disponíveis
- Dados de agendamentos (paciente, procedimento, horário)

### **Amazon Bedrock**  
Gera respostas contextualizadas usando IA, como:
- Explicações detalhadas sobre procedimentos
- Sugestões de serviços com base em sintomas descritos

### **Amazon SNS (Simple Notification Service)**  
Envia notificações automáticas para clientes:
- Confirmação de agendamento
- Lembretes pré-consulta (24h antes)

### **AWS IAM**  
Gerencia permissões entre serviços, garantindo que:
- Lambda acesse DynamoDB/Bedrock/SNS
- Lex invoque apenas funções autorizadas

## 🔒 Segurança da Aplicação

### **AWS WAF**  
Protege o site contra ataques comuns (SQL Injection, XSS).

### **AWS Shield**  
Defesa contra DDoS para garantir disponibilidade contínua.

### **Criptografia em Trânsito/Repouso**  
- Dados sensíveis criptografados no DynamoDB (AES-256)
- Comunicação via HTTPS (TLS 1.2+)

## 🚀 Fluxo de Funcionamento

1. **Acesso Inicial:**  
   - O usuário acessa o site via Route 53 + CloudFront

2. **Interação com o Chatbot:**  
   - Lex recebe a pergunta (ex: _"Tem horário para limpeza de pele amanhã?"_)

3. **Processamento Backend:**  
   - Lex aciona uma função Lambda, que:
     - Consulta o DynamoDB para verificar disponibilidade
     - Usa o Bedrock para gerar respostas naturais (ex: _"Sim! Temos às 14h ou 16h."_)

4. **Armazenamento/Notificação:**  
   - Se o usuário agendar, Lambda:
     - Registra o agendamento no DynamoDB
     - Dispara confirmação via SNS (SMS/e-mail)

## ✨ Diferenciais

- **Respostas Humanizadas:** Bedrock enriquece interações com contexto médico
- **Escalabilidade Automática:** Lambda + DynamoDB lidam com picos de demanda
- **Redução de Faltas:** Lembretes automáticos (SNS) diminuem cancelamentos

## 🚀 Evoluções Planejadas

### **💡 Aprimoramento de Inteligência**  
- Aumentar a precisão do chatbot em perguntas complexas usando:
  - Fine-tuning de modelos no Amazon Bedrock
  - Análise de feedback dos usuários via CloudWatch Logs Insights

### **⚡ Otimização de Performance**  
- Reduzir tempo de resposta para **<3s** através de:
  - Cache de respostas frequentes no Amazon ElastiCache
  - Ajuste de cold start das funções Lambda (Provisioned Concurrency)

### **🌍 Suporte Multilíngue**  
- Implementar tradução em tempo real com:
  - Amazon Translate para conversão automática
  - Dicionário médico especializado por idioma

### **💳 Pagamento Integrado**  
- Sistema seguro de pagamentos via:
  - **AWS API Gateway** como frontend de APIs
  - **Amazon Pay** para processamento transacional
  - Validação de cobrança com AWS Lambda (Python)
  - Confirmação automática via SNS após pagamento

### **📊 Métricas de Sucesso**  
- KPIs para acompanhamento:
  - `Taxa de acerto`: ≥90% em perguntas complexas (Bedrock Analytics)
  - `Latência média`: <2.8s (CloudWatch Metrics)
  - `Novos idiomas`: +2 por trimestre
  - `Conversão`: ≥70% nos agendamentos com pagamento integrado


## 🎬 Demonstração
[
![Vídeo do EstéticaBot](https://img.youtube.com/vi/IziquCU4fKU/hqdefault.jpg)](https://www.youtube.com/watch?v=IziquCU4fKU)

## 👥 Equipe

### **Scrum Masters:**  
- Jefferson Cavalcante Vieira  
- Amanda Letícia Pereira Medeiros  

### **Líder Técnico:**  
- Jefferson Cavalcante Vieira  

### **Arquitetura:**  
- Jefferson Cavalcante Vieira  
- Evandro Luiz Pagano Buxini  
- Rudolfo Wayli Nassif Maia  

### **Desenvolvedores:**  
- Alana Mirella Cunha Felix  
- Gustavo Soares  
- Nathan Silva  
- Rudolfo Wayli Nassif Maia  

<table>
  <tr>
    <td align="center" valign="top" width="120">
      <a href="https://github.com/Darkzr4" title="GitHub">
        <img src="https://avatars.githubusercontent.com/u/97708635?v=4" style="width:100px;height:100px;object-fit:cover;border-radius:50%" alt="Foto Jefferson"/><br>
        <sub><b>Jefferson Cavalcante</b></sub>
      </a>
    </td>
    <td align="center" valign="top" width="120">
      <a href="https://github.com/alanamcfelix" title="GitHub">
        <img src="https://avatars.githubusercontent.com/u/163422639?v=4" style="width:100px;height:100px;object-fit:cover;border-radius:50%" alt="Foto Alana"/><br>
        <sub><b>Alana Mirella</b></sub>
      </a>
    </td>
    <td align="center" valign="top" width="120">
      <a href="https://github.com/iamandamedeiros" title="GitHub">
        <img src="https://avatars.githubusercontent.com/u/149709202?v=4" style="width:100px;height:100px;object-fit:cover;border-radius:50%" alt="Foto Amanda"/><br>
        <sub><b>Amanda Medeiros</b></sub>
      </a>
    </td>
    <td align="center" valign="top" width="120">
      <a href="https://github.com/EvandroPBuxini" title="GitHub">
        <img src="https://avatars.githubusercontent.com/u/189387247?v=4" style="width:100px;height:100px;object-fit:cover;border-radius:50%" alt="Foto Evandro"/><br>
        <sub><b>Evandro Buxini</b></sub>
      </a>
    </td>
    <td align="center" valign="top" width="120">
      <a href="https://www.linkedin.com/in/gustavo-soares-16310b1a2/" title="LinkedIn">
        <img src="https://media.licdn.com/dms/image/v2/D4D03AQG1w_bFxaoyTg/profile-displayphoto-shrink_800_800/B4DZRgDmYoGkAc-/0/1736778345189?e=1749081600&v=beta&t=6AdVuBL9qOJgMcpvb4qTsOBO3nyFXc0hjHuAzFkVAs4" style="width:100px;height:100px;object-fit:cover;border-radius:50%" alt="Foto Gustavo"/><br>
        <sub><b>Gustavo Soares</b></sub>
      </a>
    </td>
    <td align="center" valign="top" width="120">
      <a href="https://www.linkedin.com/in/nathan-silva13/" title="LinkedIn">
        <img src="https://media.licdn.com/dms/image/v2/D5603AQFqzbWPOmTUYw/profile-displayphoto-shrink_400_400/B56ZS9xmDNGUAk-/0/1738350682921?e=1749081600&v=beta&t=HAhvgSYHFwwMmRHklKQCJF9h9lSAsoW1xmJ7YEq16BM" style="width:100px;height:100px;object-fit:cover;border-radius:50%" alt="Foto Nathan"/><br>
        <sub><b>Nathan Silva</b></sub>
      </a>
    </td>
    <td align="center" valign="top" width="120">
      <a href="https://www.linkedin.com/in/rudolfomaia/" title="LinkedIn">
        <img src="https://media.licdn.com/dms/image/v2/D4D03AQFy8ln7QMJJmg/profile-displayphoto-shrink_800_800/B4DZRgMnNAHcAg-/0/1736780707077?e=1749081600&v=beta&t=q7vfwWvjg7P9mDqETOxEgmgD0UeZw1qkTfpqPWSkBtI" style="width:100px;height:100px;object-fit:cover;border-radius:50%" alt="Foto Rudolfo"/><br>
        <sub><b>Rudolfo Maia</b></sub>
      </a>
    </td>
  </tr>
</table>

## ✅ Conclusão

O EstéticaBot representa uma solução inovadora para otimizar o atendimento em clínicas estéticas, proporcionando uma experiência mais ágil, eficiente e personalizada para os clientes. Utilizando tecnologias AWS e inteligência artificial generativa, o chatbot permite agendamentos automáticos, envio de notificações e respostas inteligentes, reduzindo a carga de trabalho da equipe e melhorando a satisfação dos usuários.

**Obrigado à [Escola da Nuvem](https://escoladanuvem.org/) e ao instrutor [Ricardo Simines](https://www.linkedin.com/in/ricardosiminesscopim/)!**
