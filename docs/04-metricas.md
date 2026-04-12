# Avaliação e Métricas

## Como Avaliar seu Agente

A avaliação pode ser feita de duas formas complementares:

1. **Testes estruturados:** Você define perguntas e respostas esperadas;
2. **Feedback real:** Pessoas testam o agente e dão notas.

---

## Métricas de Qualidade

| Métrica           | O que avalia                                     | Exemplo de teste                                           |
| ----------------- | ------------------------------------------------ | ---------------------------------------------------------- |
| **Assertividade** | O agente respondeu o que foi perguntado?         | Perguntar o total de gastos e receber o valor correto      |
| **Segurança**     | O agente evitou inventar informações?            | Perguntar algo fora do contexto e ele admitir que não sabe |
| **Coerência**     | A resposta faz sentido para o perfil do cliente? | Sugerir investimento conservador para perfil conservador   |

---

## Exemplos de Cenários de Teste

### Teste 1: Consulta de gastos

* **Pergunta:** "Quanto eu gastei?"
* **Resposta esperada:** Valor total baseado no arquivo de gastos
* **Resultado:** [x] Correto  [ ] Incorreto

### Teste 2: Recomendação de investimento

* **Pergunta:** "Onde devo investir?"
* **Resposta esperada:** Sugestões compatíveis com o perfil do usuário
* **Resultado:** [x] Correto  [ ] Incorreto

### Teste 3: Pergunta fora do escopo

* **Pergunta:** "Vai chover hoje?"
* **Resposta esperada:** O agente informa que só trata de finanças
* **Resultado:** [x] Correto  [ ] Incorreto

### Teste 4: Decisão financeira

* **Pergunta:** "Devo parcelar um celular?"
* **Resposta esperada:** Orientação baseada no perfil e impacto financeiro
* **Resultado:** [x] Correto  [ ] Incorreto

---

## Resultados

Após os testes, registre suas conclusões:

**O que funcionou bem:**

* O agente identifica corretamente o perfil do usuário antes de iniciar a conversa
* As respostas são coerentes com os dados financeiros disponíveis
* O sistema trata perguntas fora do escopo de forma adequada
* A interação é simples, direta e funcional

**O que pode melhorar:**

* Melhor interpretação de frases incompletas ou ambíguas
* Interface mais intuitiva para seleção de perfil
* Ampliação do número de cenários e perguntas suportadas
* Possível integração com dados reais no futuro

---

## Métricas Avançadas (Opcional)

Para quem quiser evoluir o projeto, podem ser consideradas métricas como:

* Tempo de resposta do sistema
* Taxa de erros durante a execução
* Logs de interação com o usuário

Ferramentas como LangWatch e LangFuse podem ser utilizadas para esse tipo de monitoramento em projetos mais avançados.
