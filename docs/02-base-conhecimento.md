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

# Nota opcional:
# Para interface (Gradio) ou modelos (Ollama), importe:
# import gradio as gr
# import ollama

# Carregando dados CSV
gastos = pd.read_csv('data/gastos_usuario.csv')

# Carregando dados JSON
with open('data/perfil_usuario.json', 'r') as f:
    perfil = json.load(f)
```

### Como os dados são usados no prompt?

Os dados servem como contexto estruturado, incluindo perfil, histórico de gastos e cenários financeiros, para orientar a geração de respostas.

Exemplo de dados utilizados:

Perfil do usuário:
- Nome: João Silva
- Renda mensal: 5000
- Objetivo: Construir reserva de emergência

Gastos mensais:
- Moradia: 1200
- Alimentação: 570
- Transporte: 295
- Saúde: 188
- Lazer: 55,90

Situação analisada:
- Pergunta: "Devo parcelar uma compra?"
- Contexto: usuário com gastos recorrentes e necessidade de manter controle financeiro

Com base nesses dados, o agente avalia o impacto da decisão e fornece orientações adequadas, considerando o equilíbrio financeiro do usuário.

Os dados são incluídos como contexto no prompt, permitindo que o agente gere respostas mais consistentes e alinhadas às informações disponíveis.

## Exemplo de Contexto Montado

> Exemplo de como os dados são organizados e apresentados ao agente para auxiliar na geração de respostas.
```
    Dados do Usuário:
    - Nome: João Silva
    - Idade: 32
    - Profissão: Analista de Sistemas
    - Renda mensal: R$ 5.000
    - Objetivo: Construir reserva de emergência
    - Reserva atual: R$ 10.000

    Resumo financeiro:
    - Moradia: R$ 1.380
    - Alimentação: R$ 570
    - Transporte: R$ 295
    - Saúde: R$ 188
    - Lazer: R$ 55,90

    Situação atual:
    - Usuário deseja saber se deve realizar uma nova compra ou parcelamento
    - Gastos já comprometem parte significativa da renda mensal

    Referência de decisões anteriores:
    - Avaliar liquidez antes de investir
    - Manter controle de gastos mensais
    - Priorizar estabilidade financeira

    Instrução para o agente:
    Com base nos dados acima, analise a situação e forneça uma orientação financeira clara e responsável, considerando o impacto da decisão no orçamento do usuário.
```
