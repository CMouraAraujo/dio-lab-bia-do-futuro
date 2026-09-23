# Base de Conhecimento

## Dados Utilizados

Descreva se usou os arquivos da pasta `data`, por exemplo:

| Arquivo | Formato | Utilização no Agente |
|---------|---------|---------------------|
| `historico_interacoes.csv` | CSV | Contextualizar interações anteriores |
| `perfil_rotina.json` | JSON | Perfil de rotinas por recomendações |
| `sugestoes_rotina.json` | JSON | Sugerir rotinas adequados ao perfil |
| `registro_atividades.csv` | CSV | Analisar padrão de atividades dos clientes |

---

## Adaptações nos Dados

> Você modificou ou expandiu os dados mockados? Descreva aqui.

Os dados foram modificados para explicar como são rotinas mais produtivas, mostrar um histórico interações anteriores, sugerir rotinas e com isso criar uma melhor rotina para o usuário.

---

## Estratégia de Integração

### Como os dados são carregados?
> Descreva como seu agente acessa a base de conhecimento.

Os JSON/CSV são carregados no início da sessão e incluídos no contexto do prompt para o modelo de IA. Os dados serão carregados 
via código Python utilizando bibliotecas como Pandas

### Como os dados são usados no prompt?
> Os dados vão no system prompt? São consultados dinamicamente?

Os dados serão utilizados no system prompt do modelo e consultados constantemente para que não haja alucinações do modelo

---

## Exemplo de Contexto Montado

> Mostre um exemplo de como os dados são formatados para o agente.

```
Dados do Cliente:
- Nome: Marina Costa
- Idade: 29
- Carga horaria semanal: 40
- Objetivo principal: Criar uma rotina mais equilibrada entre trabalho, saúde e descanso
...

Metas:
- Meta: Dormir pelo menos sete horas por noite
- Meta: Praticar atividade física três vezes por semana
...
```
