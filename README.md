# EsteticaBot - Documentação do Projeto

---

## Equipe
- **Scrum Master:** [Jefferson Cavalcante Vieira](https://www.linkedin.com/in/jeff-cav22/)
- **Líder Técnica:** [Amanda Letícia Pereira Medeiros](https://www.linkedin.com/in/iamandamedeiros/)
- **Desenvolvedores:** [Gustavo Soares](https://www.linkedin.com/in/gustavo-soares-16310b1a2/), [Evandro Luiz Pagano Buxini](https://www.linkedin.com/in/evandro-pagano-buxini-engenheiro-de-computacao-em-formacao-em-transicao/), [Alana Mirella Cunha Felix](https://www.linkedin.com/in/alana-felix/)
- **Arquitetos:** [Jefferson Cavalcante Vieira](https://www.linkedin.com/in/jeff-cav22/), [Nathan da Silva](https://www.linkedin.com/in/nathan-silva13/), [Rudolfo Wayli Nassif Maia](https://www.linkedin.com/in/rudolfomaia/)

---

## Objetivo do Projeto

Este projeto tem como finalidade desenvolver uma solução inovadora de Inteligência Artificial utilizando a linguagem de programação Python, integrando um modelo de linguagem fornecido pelo Amazon Bedrock, com o objetivo de criar um chatbot interativo e altamente eficiente para assistência em clínicas estéticas.

### Habilidades Exercitadas
- Técnicas: Python, arquitetura de software, data sourcing e integração com IA
- Organizacionais: comunicação, colaboração em equipe e gestão de projetos

---

## Proposta de Valor

- **Experiência Personalizada**
- **Facilidade no Agendamento**
- **Redução de Cancelamentos**
- **Eficiência Operacional**
- **Acessibilidade e Conveniência**

---

## Solução

O EsteticaBot é um chatbot capaz de:
- Atender clientes da clínica estética com informações sobre serviços, preços e horários disponíveis.
- Permitir agendamentos automáticos de consultas.
- Enviar notificações para confirmação e lembrete de atendimentos.
- Responder de forma natural e personalizada utilizando IA generativa do Amazon Bedrock.
- Garantir um tempo de resposta rápido e uma interface intuitiva.

---

## Metodologia Ágil
- **Kanban**
- Ferramentas utilizadas: [Notion](https://www.notion.so/Documenta-o-EsteticaBot-189bc90f5d0f803893cac65bd6515bf2?pvs=4)

---

## Requisitos

### Funcionais
- **Implementação do serviço utilizando a linguagem Python e boto3.**
- **Utilização do Amazon S3 para armazenamento e do Amazon Bedrock (Claude 3.5 Sonnet v2) para geração de respostas inteligentes.**
- **Uso do Amazon Lex para criação da interface de conversação do chatbot.**
- **Utilização do DynamoDB para armazenar informações dos clientes e agendamentos.**
- **Notificações automatizadas via Amazon SNS.**
- **Garantia de armazenamento seguro dos dados no DynamoDB e S3.**
- **Controle de acesso configurado via AWS IAM.**

### Não Funcionais
- **O chatbot deve garantir alta responsividade, oferecendo tempos de resposta inferiores a 5 segundos:** Tempo de resposta rápido
- **O desenvolvimento será realizado utilizando a linguagem Python com boto3 para interação com AWS:** Python com biblioteca Boto3 e Amazon Bedrock
- **O sistema utilizará o Amazon Bedrock para processar e gerar respostas personalizadas, com base na documentação disponibilizada.**

---

## Serviços AWS

- **IAM:** Garante a segurança da aplicação, controlando quem acessa quais recursos da AWS e com quais permissões.
- **Route 53:** Direciona o tráfego de internet para a aplicação, atuando como um DNS inteligente, otimizando a rota para o usuário.
- **CloudFront:** Acelera a entrega de conteúdo estático da aplicação, como imagens e scripts, para os usuários, melhorando a performance.
- **Lex:** Permite criar interfaces de chatbot, para interagir com os usuários de forma natural e intuitiva.
- **DynamoDB:** Armazena dados de forma flexível e escalável, para armazenar informações dos usuários e agendamentos.
- **Bedrock (Claude 3.5 Sonnet v2):** Amazon Bedrock (Titan Text G1 - Premier)
- **Lambda:** Orquestração do fluxo de interação entre Lex, Bedrock e DynamoDB.
- **Boto3:** Biblioteca Python para interação com AWS

---

## Arquitetura

O EsteticaBot foi projetado inicialmente como um Produto Mínimo Viável (MVP), com ênfase em:
- Python
- Amazon Bedrock
- DynamoDB

![Fluxograma da arquitetura](https://i.imgur.com/YmGjPF5.png)

- Usuário (Site): O cliente acessa o site, onde pode interagir com o Amazon Lex.
Aqui, Route 53 e CloudFront entram para garantir a entrega de conteúdo de forma rápida e a resolução do DNS.

- Amazon Lex: O Amazon Lex recebe a interação do usuário e começa a processar as perguntas, como "Quais serviços a clínica oferece?" ou "Qual o preço de um procedimento?"

- AWS Lambda (Python + Boto3): O AWS Lambda é acionado por Lex e executa as funções backend, como acessar o banco de dados (DynamoDB) ou interagir com outros serviços (como SNS para notificações ou Bedrock para geração de respostas). As funções são escritas em Python, e o Boto3 permite que o código interaja com a AWS (como armazenar agendamentos no DynamoDB).

- Amazon DynamoDB: O DynamoDB armazena dados relacionados aos serviços oferecidos, horários, preços e informações dos agendamentos. Ele pode ser consultado a partir das funções Lambda para verificar a disponibilidade de horários e criar ou atualizar os agendamentos.

- Amazon Bedrock: O Bedrock é usado para personalizar a resposta ao usuário com base nas perguntas feitas, usando modelos pré-treinados para gerar respostas mais sofisticadas.

- Amazon SNS: Após a interação e agendamento, o SNS envia notificações para os usuários com confirmações e lembretes de agendamento.

- IAM: O IAM gerencia as permissões e acessos entre os serviços AWS, garantindo que as funções Lambda tenham acesso ao DynamoDB, SNS, Bedrock, etc.

### Evoluções Planejadas
- Aprimorar a precisão do chatbot na resposta a perguntas complexas.
- Otimizar o tempo de resposta para menos de 3 segundos.
- Implementar suporte a múltiplos idiomas.
- Adicionar método de pagamento integrado, utilizando o AWS API Gateway, integrando o Amazon Pay.

---

## Links Importantes
- [Notion](https://www.notion.so/Documenta-o-EsteticaBot-189bc90f5d0f803893cac65bd6515bf2?pvs=4)

---

## Demonstação
[![Vídeo do EstéticaBot](https://img.youtube.com/vi/IziquCU4fKU/hqdefault.jpg)](https://www.youtube.com/watch?v=IziquCU4fKU)


---

## Conclusão

O EstéticaBot representa uma solução inovadora para otimizar o atendimento em clínicas estéticas, proporcionando uma experiência mais ágil, eficiente e personalizada para os clientes. Utilizando tecnologias AWS e inteligência artificial generativa, o chatbot permite agendamentos automáticos, envio de notificações e respostas inteligentes, reduzindo a carga de trabalho da equipe e melhorando a satisfação dos usuários.

**Obrigado à [Escola da Nuvem](https://escoladanuvem.org/) e ao instrutor [Ricardo Simines](https://www.linkedin.com/in/ricardosiminesscopim/)!**
