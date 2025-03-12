# EstéticaBot – Assistente Inteligente para Clínicas Estéticas

## 📌 Descrição Geral
O **EstéticaBot** é um chatbot baseado em IA desenvolvido para clínicas estéticas. Ele permite que clientes realizem cadastros, tirem dúvidas, agendem atendimentos e recebam notificações automáticas sobre suas consultas. O sistema utiliza diversas tecnologias da **Amazon AWS** para garantir escalabilidade, segurança e eficiência.

---

## 🏗️ Arquitetura e Tecnologias Utilizadas

### **1. Interface do Usuário – Site Estático**
- **AWS EC2**: Hospedagem do site estático.
- **Amazon S3 + CloudFront** *(Alternativa)*: Para distribuir conteúdo com melhor desempenho.

### **2. Inteligência Artificial para Atendimento – Chatbot IA**
- **Amazon Lex**: Chatbot com IA para interação com clientes e processamento de linguagem natural (NLP).
- **Amazon Comprehend** *(Opcional)*: Para análise de sentimentos e identificação de palavras-chave.
- **Amazon Polly** *(Opcional)*: Conversão de texto em fala para interações por voz.

### **3. Processamento e Armazenamento dos Dados**
- **Amazon RDS (MySQL/PostgreSQL)**: Banco de dados para armazenar cadastros e agendamentos.
- **AWS Lambda**: Funções serverless para processar pedidos do chatbot e registrar reservas no banco de dados.

### **4. Notificações e Confirmação de Agendamentos**
- **Amazon SNS**: Envio de SMS e notificações push para confirmação de reservas.
- **Amazon SES**: Envio de e-mails automáticos com detalhes da consulta.
- **AWS Lambda + EventBridge**: Agendamento de lembretes automáticos antes da consulta.

---

## 🔄 Fluxo de Funcionamento
1. O cliente acessa o site e interage com o chatbot para tirar dúvidas e agendar um atendimento.
2. O **Amazon Lex** interpreta a solicitação e verifica disponibilidade no banco de dados (**RDS**).
3. O agendamento é registrado automaticamente via **AWS Lambda**.
4. O cliente recebe uma notificação via **Amazon SNS** (SMS) ou **Amazon SES** (e-mail) com a confirmação.
5. No dia anterior à consulta, um lembrete automático é enviado solicitando confirmação.

---

## ✅ Benefícios da Arquitetura
- **🔹 Automação Total** – Atendimento 24/7 sem necessidade de intervenção humana.
- **🔹 Escalabilidade** – Capacidade de crescer conforme a demanda.
- **🔹 Redução de Custos** – Utilização de serviços serverless evita gastos desnecessários.
- **🔹 Experiência Melhorada para o Cliente** – Atendimento rápido e notificações automáticas.

---

## 🚀 Expansões Futuras
- Integração com **WhatsApp** usando **Twilio + Amazon Lex**.
- Implementação de **Amazon Pay** para pagamento antecipado das consultas.
- Análise de feedbacks com **Amazon Comprehend** para aprimorar respostas do chatbot.

---

## 🛠️ Como Executar o Projeto
1. **Configurar o ambiente AWS:**
   - Criar uma instância EC2 ou configurar S3 para hospedagem do site.
   - Criar um chatbot no **Amazon Lex**.
   - Configurar um banco de dados no **Amazon RDS**.
   - Criar funções **AWS Lambda** para processar reservas.
   - Configurar **Amazon SNS/SES** para envio de notificações.
2. **Deploy do Site:** Fazer upload dos arquivos HTML/CSS no EC2 ou S3.
3. **Testar o Chatbot:** Utilizar a interface do **Amazon Lex** para verificar as respostas.
4. **Monitorar e Ajustar:** Configurar logs no **Amazon CloudWatch** para monitoramento do desempenho.

---

## 📄 Licença
Este projeto é um conceito acadêmico desenvolvido para fins educacionais. 

---

💡 **Desenvolvido como parte do curso Re/Start 2 da Escola da Nuvem.**
