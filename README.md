# Tobias - Assistente de Decisão Financeira

Chatbot desenvolvido em Python com foco em auxiliar usuários na tomada de decisões financeiras do dia a dia, utilizando análise de perfil, dados simulados e lógica de interpretação de mensagens.

---

## Sobre o Projeto

O Tobias é um assistente virtual que simula um consultor financeiro. Ele analisa informações do usuário, como renda, saldo e perfil de risco, e responde de forma personalizada a perguntas relacionadas a:

* Controle de gastos
* Reserva de emergência
* Parcelamentos
* Investimentos

O projeto utiliza dados estruturados em arquivos JSON e CSV para gerar respostas contextualizadas.

---

## Diferenciais

* Identificação de perfil antes do início da conversa
* Respostas personalizadas com base em dados financeiros
* Interpretação de intenções do usuário (ex: "parcelar", "investir", "guardar")
* Tratamento de perguntas fora do escopo
* Fluxo conversacional simples e funcional

---

## Tecnologias Utilizadas

* Python
* Pandas
* Gradio
* JSON e CSV

---

## Estrutura do Projeto

```
dio-lab-bia-do-futuro/
│
├── data/
│   ├── perfil_usuario.json
│   ├── situacoes_financeiras.json
│   ├── gastos_usuario.csv
│   └── decisoes_financeiras.csv
│
├── app.py
└── README.md
```

---

## Como Executar

1. Clone o repositório:

```
git clone https://github.com/julianasilvadealmeida808-rgb/dio-lab-bia-do-futuro.git
```

2. Acesse a pasta do projeto:

```
cd dio-lab-bia-do-futuro
```

3. Instale as dependências:

```
pip install pandas gradio
```

4. Execute a aplicação:

```
python app.py
```

5. Acesse no navegador:

```
http://127.0.0.1:7860
```

---

## Exemplo de Uso

```
Usuário: oi  
Assistente: Olá. Informe seu perfil para iniciar.

Usuário: Juliana  
Assistente: Perfil selecionado com sucesso.

Usuário: devo parcelar um celular?  
Assistente: resposta baseada no perfil financeiro
```

---

## Aprendizados

* Manipulação de dados com Pandas
* Estruturação de lógica condicional
* Criação de interfaces com Gradio
* Tratamento de entradas do usuário
* Construção de fluxo conversacional

---

## Melhorias Futuras

* Interface com seleção de perfil (dropdown)
* Persistência de histórico de conversa
* Interpretação mais avançada de linguagem natural
* Integração com APIs reais

---

## Autora

Juliana Almeida

---

## Agradecimentos

Projeto desenvolvido com base nos conteúdos da DIO.
