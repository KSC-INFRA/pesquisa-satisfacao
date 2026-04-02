# Projeto: Automação e Integridade de Dados - Pesquisa CSAT (CX)

### Visão Geral do Projeto
Na **King Star Colchões**, havia a necessidade de automatizar a coleta de satisfação (CSAT) após o atendimento no Zendesk, garantindo que os dados fossem auditáveis e imunes a tentativas de autoavaliação por parte dos colaboradores. A necessidade da empresa é receber notas CSAT de 1 a 5, solução que não é nativa do Zendesk, visto que ele oferece apenas satisfeito ou insatisfeito como resposta do gatilho padrão de pesquisa.

---

## 🎯 O Desafio
O objetivo principal foi criar um fluxo automatizado e seguro que garantisse a integridade dos dados de satisfação do cliente, prevenindo fraudes internas e otimizando o processo de fechamento de tickets.

---

## 🛠️ Tecnologias Utilizadas
- **Zendesk API:** Gestão de tickets, triggers e campos customizados.
- **GitHub:** Hospedagem do Front-end da pesquisa.
- **Google Apps Script:** Motor de integração (Backend) e processamento via POST.
- **JavaScript:** Lógica de captura de parâmetros, validação de segurança e envio de dados.

---

## 🏗️ Arquitetura da Solução
O projeto foi dividido em **4 fases críticas** para garantir que o dado saia do cliente e chegue ao relatório de forma limpa:

1. **Disparo (Zendesk):** O fluxo inicia com uma macro que prepara o ticket (`tag: csat_enviada`), muda o status para "**Resolvido**" e gera um link único contendo o ID do ticket.
2. **Interface de Coleta (GitHub):** Uma página web leve, hospedada no GitHub, captura o ID do ticket via URL e apresenta uma escala de 1 a 5 para o cliente.
3. **Integração e Inteligência (Apps Script):** O motor recebe a nota via POST, autentica-se na API do Zendesk e realiza a gravação no campo customizado "**Nota CSAT**".
4. **Fechamento de Ciclo:** Um gatilho final no Zendesk identifica a nota, mudando o status do ticket de "**Resolvido**" para "**Fechado**" instantaneamente.

---

## 🛡️ Camadas de Segurança e Auditoria
Como analista, foquei na integridade do dado. Implementei três travas de segurança essenciais:

- **Geofencing de IP:** Bloqueio automático de qualquer acesso originado da rede interna ou Wi-Fi corporativo da empresa.
- **Validação de Referer:** Identificação e bloqueio de redirecionamentos suspeitos vindos diretamente da interface do agente.
- **Log de Fraude:** Tentativas indevidas são registradas e auditadas para a equipe de Qualidade.

---

## ✅ Resultados Obtidos
- **Inteligência de Negócio (Data-Driven):** A viabilização da coleta efetiva das notas (escala de 1 a 5) permitiu à empresa mensurar a real satisfação dos clientes, destravando a capacidade da gestão de avaliar cenários e tomar decisões estratégicas baseadas em dados concretos.
- **Eficiência Operacional:** Eliminação total do processo manual de fechamento de tickets após o envio da pesquisa.
- **Qualidade dos Dados:** Redução a zero de avaliações fraudulentas ou internas, garantindo a total veracidade das métricas coletadas.
- **Governança:** Acesso restrito às notas apenas para a liderança e o time de Qualidade.

---

## 🔗 Links e Contato
- **Repositório:** `Luiznascimento6599/projeto_CSAT`
- **Autor:** Luiz Torres Nascimento
- **LinkedIn:** [Luiz Torres Nascimento](https://www.linkedin.com/in/luiz-nascimento-52103322a/)
