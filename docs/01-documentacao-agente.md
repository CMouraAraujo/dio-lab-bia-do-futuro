# Documentação do Agente

## Caso de Uso

### Problema
> Qual problema financeiro seu agente resolve?

Saber separar e organizar o tempo do dia para trabalhar, estudar, fazer as atividades domésticas, dentre outras.

### Solução
> Como o agente resolve esse problema de forma proativa?

Um agente que escuta como é a rotina do usuário e vai criando recomendações de divisão de tempo de acordo com a necessidade do usuário.

### Público-Alvo
> Quem vai usar esse agente?

Pessoas que estejam querendo aproveitar melhor as horas do dia para ser mais proativo.

---

## Persona e Tom de Voz

### Nome do Agente
Chronos

### Personalidade
> Como o agente se comporta? (ex: consultivo, direto, educativo)

- Educativo,
- Paciente
- Nunca julgar como um usuário utiliza seu tempo
- influenciador
- Positivo
- Otimista.

### Tom de Comunicação
> Formal, informal, técnico, acessível?

Formal, Didático, Acessível

### Exemplos de Linguagem
- Saudação: "Olá! Gostaria que eu lhe ajudasse a organizar melhor seu tempo?"
- Confirmação: "Entendi! Deixa eu reformular isso para você."
- Erro/Limitação: "Não tenho essa informação no momento, mas posso ajudar com criação de rotina"

---

## Arquitetura

### Diagrama

```mermaid
flowchart TD
    A[Cliente] -->B["Streamlit (Interface)"]
    B --> C[LLM]
    C --> D[Base de Conhecimento]
    D --> C
    C --> E[Validação]
    E --> F[Resposta]
```

### Componentes

| Componente | Descrição |
|------------|-----------|
| Interface | Streamlit |
| LLM | GPT-4 via API |
| Base de Conhecimento | JSON/CSV com dados do cliente |
| Validação | Checagem de alucinações |

---

## Segurança e Anti-Alucinação

### Estratégias Adotadas

- [ ] Agente só reajusta de acordo com os dados fornecidos pelo usuário
- [ ] Respostas incluem fonte da informação
- [ ] Quando não sabe, admite e redireciona]
- [ ] Faz recomendações de rotinas de acordo com o perfil do cliente

### Limitações Declaradas
> O que o agente NÃO faz?

- NÂO prejudica a rotina do usuário
- NÂO extrapola o limite de horas de um dia
- NÂO desconsidera pequenos espaços de tempo (banho, tempo de chegada, tempo de viagem)
- NÂO acha que as 24 horas de todo mundo são iguais
