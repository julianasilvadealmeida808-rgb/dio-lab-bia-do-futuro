# Base de Conhecimento

## Dados Utilizados

Descreva se usou os arquivos da pasta `data`, por exemplo:

| Arquivo | Formato | Utilização no Agente |
|---------|---------|---------------------|
| `perfil_usuario.json` | JSON | Armazenar informações básicas como renda e limites do usuário |
| `gastos_usuario.csv` | CSV | Representar os gastos mensais organizados por categoria |
| `situacoes_financeiras.json` | JSON | Fornecer exemplos de decisões financeiras e orientações |
| `decisoes_financeiras.csv` | CSV | Simular cenários de decisões financeiras e apoiar o agente na geração de orientações |

---

## Adaptações nos Dados

Os dados foram adaptados conceitualmente para representar cenários de tomada de decisão financeira, em vez de recomendações de investimento. As informações foram utilizadas como base simulada para orientar o usuário em situações como compras, controle de gastos e avaliação de impacto financeiro.

---

## Estratégia de Integração

### Como os dados são carregados?

Os dados são considerados como carregados no início da interação e utilizados como contexto para o agente. Em um cenário real, esses dados poderiam ser carregados por meio de código a partir de arquivos JSON e CSV.

Exemplo:

```python
import json
import pandas as pd
import gradio as gr
import ollama

# Carregando dados CSV
gastos = pd.read_csv('data/gastos_usuario.csv')
decisoes = pd.read_csv('data/decisoes_financeiras.csv')

# Carregando dados JSON
with open('data/perfil_usuario.json', 'r') as f:
    perfil = json.load(f)

with open('data/situacoes_financeiras.json', 'r') as f:
    situacoes = json.load(f)

# Exemplo de uso:
# - gradio pode criar uma interface simples para interação
# - ollama pode rodar modelos locais usando esses dados como contexto

# Agora o agente tem acesso a:
# - perfil: informações básicas do usuário
# - gastos: entradas e saídas mensais
# - situacoes: dilemas financeiros cotidianos
# - decisoes: histórico de decisões e orientações
```

### Como os dados são usados no prompt?

Os dados servem como contexto estruturado, incluindo perfil, histórico de gastos e cenários financeiros, para orientar a geração de respostas.

Exemplo de dados utilizados:
```
Perfil do usuário:
• 	Nome: Helena Lima
• 	Renda mensal: 4500
• 	Saldo atual: 1500
• 	Aceita risco: sim
• 	Objetivo: Investir parte da renda em aplicações de baixo risco e manter equilíbrio entre consumo e reserva
Gastos mensais:
• 	Moradia: 1200
• 	Alimentação: 570
• 	Transporte: 295
• 	Saúde: 188
• 	Lazer: 55,90
Situação analisada:
• 	Pergunta: "Devo parcelar a compra de um celular em 12 vezes?"
• 	Contexto: Helena possui gastos recorrentes, saldo limitado e objetivo de investir parte da renda. O parcelamento pode comprometer sua capacidade de manter reservas e investir.

Decisão simulada:
• 	Orientação: Avaliar sobra mensal após despesas essenciais e verificar se o parcelamento não compromete a meta de investimento.
• 	Resultado: Orientado — recomendação de evitar parcelamento longo e priorizar liquidez para manter equilíbrio financeiro.
Com base nesses dados, o agente avalia o impacto da decisão e fornece orientações adequadas, considerando o perfil de risco de Helena e seus objetivos.
Os dados são incluídos como contexto no prompt, permitindo que o agente gere respostas mais consistentes e alinhadas às informações disponíveis.

## Exemplo de Contexto Montado

> Exemplo de como os dados são organizados e apresentados ao agente para auxiliar na geração de respostas.

Dados do Usuário:
- Nome: Helena Lima
- Idade: 28 anos
- Profissão: Designer Gráfico
- Renda mensal: R$ 4.500
- Saldo atual: R$ 1.500
- Aceita risco: Sim
- Objetivo: Investir parte da renda em aplicações de baixo risco e manter equilíbrio entre consumo e reserva

Resumo Financeiro:
- Moradia: R$ 1.200
- Alimentação: R$ 570
- Transporte: R$ 295
- Saúde: R$ 188
- Lazer: R$ 55,90


Situação atual:
- Helena avalia se deve parcelar a compra de um celular em 12 vezes. Como seus gastos já comprometem parte significativa da renda, o parcelamento pode reduzir a capacidade de investir e manter reservas.

Referência de decisões anteriores:
- Ela costuma avaliar sobra mensal antes de assumir novas parcelas, manter liquidez para garantir reservas e priorizar equilíbrio entre consumo e investimento.

Instrução para o agente:
- Com base nesse contexto, forneça uma orientação financeira clara e responsável, considerando o impacto da decisão no orçamento e nos objetivos de investimento da usuária.
```
