# 📚 Organizador e Notificador Automático de Estudos com n8n, Google Sheets e Gmail

## 🎯 Problema Resolvido
Estudantes e profissionais frequentemente acumulam tarefas, prazos e matérias espalhados em planilhas, perdendo o controle de datas importantes ou esquecendo de acompanhar o status de entregas pendentes. O desafio era eliminar o trabalho manual de verificar a planilha todos os dias e garantir lembretes automáticos inteligentes.

## 🛠️ Solução Implementada
Desenvolveu-se uma automação completa utilizando a ferramenta **n8n** (self-hosted) integrada ao ecossistema do **Google Cloud (Google Sheets e Gmail)**. O fluxo roda autonomamente em segundo plano, garantindo que:
1. **Leitura de Dados:** O n8n acessa periodicamente a planilha de controle de estudos ("estudos", aba "Atividades").
2. **Filtro Inteligente (If):** Identifica dinamicamente apenas as tarefas cujo status seja exatamente `Pendente` e valida se o prazo da atividade ainda está vigente (até a data atual).
3. **Agregação de Dados (Aggregate):** Agrupa todas as tarefas pendentes filtradas em um único bloco consolidado.
4. **Disparo Automatizado (Gmail):** Envia um único e-mail diário formatado e estruturado diretamente para o aluno com a lista completa de pendências.

---

## ⚙️ Arquitetura do Fluxo
* **Schedule Trigger:** Aciona a automação diariamente no horário configurado.
* **Google Sheets Node:** Lê as linhas da planilha de tarefas.
* **If Node:** Filtra as linhas por status "Pendente" e validação de data (`DateTime`).
* **Aggregate Node:** Consolida os múltiplos itens em uma única lista em formato de texto/HTML.
* **Gmail Node:** Dispara a notificação consolidada via API do Google.

---

