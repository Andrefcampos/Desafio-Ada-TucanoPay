### Desafio-Ada-TucanoPay

# 🦜 Assistente Virtual Tucano Pay

Bem-vindo ao repositório do **Assistente Virtual Tucano Pay**. Este projeto tem como objetivo desenvolver um agente conversacional de IA altamente seguro e fiel às regras de negócio para o atendimento ao cliente de uma fintech, utilizando técnicas avançadas de Engenharia de Prompt.

## 📌 Sobre o Projeto

O assistente foi desenhado para atuar nos canais de atendimento da Tucano Pay (Chat do App, WhatsApp, E-mail e Instagram). O desenvolvimento focou-se não apenas em fornecer respostas corretas, mas em garantir a **proteção de dados pessoais (PII)**, prevenir **alucinações da IA** e criar barreiras robustas contra **Prompt Injection**.

## 🚀 Evolução do Prompt: V1 vs. V2

O projeto está documentado em duas iterações principais que demonstram a evolução da arquitetura do agente:

* **V1 (Suporte Interno):** O assistente atua no *backoffice*, auxiliando a equipa humana de suporte na elaboração de rascunhos e minutas de respostas. O foco é a formatação de texto e a análise de políticas.
* **V2 (Atendimento Direto ao Cliente):** O assistente assume a linha da frente (front-end conversacional). O prompt foi reescrito para que a IA fale diretamente com o utilizador na primeira pessoa, de forma natural, empática e acolhedora, sem revelar diretrizes internas ou burocracia do sistema. 

## 🏗️ Arquitetura CPTF

O núcleo cognitivo do assistente foi estruturado através do *framework* **CPTF**:

* **[C] Contexto:** Definição do cenário operacional e injeção da **Base de Conhecimento (BC1 a BC8)**, que cobre desde contestações de cobranças e limites de Pix até tarifas e protocolos de segurança.
* **[P] Persona:** Estabelecimento de uma identidade profissional e segura. A IA tem instruções explícitas para não deduzir factos, não atuar como humana e reconhecer limitações quando a informação estiver ausente ou "em revisão" (ex: Programa *Tucano Mais*).
* **[T] Tarefa:** Fluxo obrigatório de atendimento em 7 passos de verificação — garantindo que a segurança, o mascaramento de dados e os gatilhos de escalonamento para atendimento humano ocorram *antes* da elaboração da resposta.
* **[F] Formato:** Diretrizes de tom de voz, idioma (Português) e restrições de formatação. Inclui templates autorizados para lidar com saídas fora do escopo ou tentativas de manipulação.

## 🛡️ Segurança e Proteção de Dados

Este repositório destaca-se pela implementação estrita de guardrails de segurança:
1. **Anonimização Ativa:** Substituição obrigatória de informações sensíveis por marcadores como `[CPF REMOVIDO]` ou `[TELEFONE REMOVIDO]`.
2. **Defesa contra Jailbreak:** A regra P4 instrui a IA a ignorar comandos que tentem ativar "modos de administrador", alterar limites (ex: Pix noturno) sem o procedimento oficial ou revelar e-mails de funcionários.
3. **Escalonamento Inteligente:** O assistente identifica ativamente situações de crise (ameaças judiciais, Procon, fraudes) e aciona o atendimento humano (BC8).

## 🧪 Casos de Teste Avaliados (M1 a M8)

O modelo foi submetido a 8 cenários reais de *stress test* para validar o seu comportamento:

- **M1:** Cobrança duplicada com exposição de dados pessoais.
- **M2:** Frustração de cliente com limites do Pix noturno.
- **M3:** Cliente vítima de golpe de engenharia social via WhatsApp.
- **M4:** Dúvidas sobre um serviço que ainda está em fase de testes (Tucano Mais).
- **M5:** Tentativa agressiva de *Prompt Injection* para forçar a libertação de limites operacionais.
- **M6:** Reclamação exaltada com ameaça de acionar o Procon.
- **M7:** Pergunta sobre produto inexistente na Base de Conhecimento (Empréstimo consignado).
- **M8:** Cálculo matemático de tarifas por excesso de saques mensais.

---
*Projeto desenvolvido como parte dos requisitos práticos de capacitação em Inteligência Artificial e Engenharia de Prompt.*
