# 🧩 Atividade PBL – Aula 12  
# BDD e Automação Orientada a Comportamento – LocalEats

## 📌 Contexto

Após evoluir a qualidade do sistema LocalEats com:

- Planejamento de testes
- Testes manuais
- Testes unitários com TDD
- Testes funcionais automatizados

A equipe de Qualidade agora precisa avançar para um novo nível:

👉 Transformar requisitos e comportamentos do sistema em cenários executáveis utilizando BDD (Behavior-Driven Development).

Até agora:

- Os testes estavam muito focados na implementação
- Os fluxos eram descritos apenas tecnicamente
- Existia dificuldade em alinhar negócio, desenvolvimento e qualidade

Agora, o desafio é:

👉 Descrever o comportamento esperado do sistema de forma legível e automatizável.

O sistema ainda apresenta problemas como:

- Ambiguidade nos requisitos
- Dificuldade em validar comportamento esperado
- Falta de documentação viva
- Testes difíceis de entender por pessoas não técnicas
- Fragilidade em automações após mudanças na interface

A equipe precisa garantir que:

> “Os comportamentos esperados do sistema estejam claramente documentados e automaticamente validados.”

Para isso, será adotado:

- BDD (Behavior-Driven Development)
- Escrita de cenários em Gherkin
- Automação orientada a comportamento
- Integração entre pytest-bdd e Playwright

👉 Link para o sistema LocalEats:

https://local-eats-unisenac.vercel.app/

---

# 🎯 Objetivo da Atividade

Aplicar, de forma prática e orientada ao uso real:

- Escrita de cenários BDD
- Linguagem Gherkin
- Estrutura Given-When-Then
- Automação orientada a comportamento
- Uso de pytest-bdd
- Integração com Playwright
- Separação entre comportamento e implementação
- Organização e manutenção de testes automatizados

⚠️ Importante

O foco desta atividade NÃO é apenas automatizar cliques.

👉 O principal objetivo é:

Transformar regras e comportamentos do sistema em cenários compreensíveis por pessoas técnicas e não técnicas.

Utilizar obrigatoriamente:

- Python
- pytest
- pytest-bdd
- Playwright
- VSCode

---

# 📝 Tarefas

## 🔹 1. Fluxo escolhido

Selecionar um fluxo do sistema por integrante do grupo.

👉 Cada integrante deverá trabalhar com um comportamento diferente.

### Fluxos sugeridos

- Busca de restaurantes
- Navegação entre páginas
- Histórico de pedidos
- Visualização de restaurantes
- Filtro por categoria

---

## 🔹 2. Escrita dos cenários BDD

Criar cenários utilizando Gherkin.

### Estrutura obrigatória

```gherkin
Feature:
Scenario:
Given
When
Then
```

### Exemplo

```gherkin
Feature: Histórico de pedidos

  Scenario: Visualizar pedidos realizados
    Given que o usuário acessa a página de pedidos
    When visualizar o histórico de transações
    Then o sistema deve exibir os pedidos cadastrados
```

---

## 🔹 3. Implementação da automação com pytest-bdd

### Estrutura mínima

```text
features/
  historico_pedidos.feature

tests/
  test_historico_pedidos.py
```

### Exemplo simplificado

```python
from pytest_bdd import scenarios, given, when, then

scenarios('../features/historico_pedidos.feature')


@given('que o usuário acessa a página de pedidos')
def acessar_pagina(page):
    page.goto('https://local-eats-unisenac.vercel.app/static/orders.html')


@when('visualizar o histórico de transações')
def visualizar(page):
    page.locator('text=Histórico de Transações').is_visible()


@then('o sistema deve exibir os pedidos cadastrados')
def validar(page):
    assert page.locator('text=Pedido #1').is_visible()
```

---

## 🔹 4. Organização do projeto

```text
projeto/
│
├── features/
├── tests/
├── evidencias/
└── README.md
```

---

## 🔹 5. Execução dos testes

```bash
pytest
```

Registrar:

- total de cenários
- cenários aprovados
- cenários falhos
- prints ou logs

---

## 🔹 6. Análise crítica

Responder:

- O cenário ficou legível?
- O BDD ajudou a entender o comportamento?
- O teste ficou robusto?
- Quais dificuldades surgiram?
- O teste ficou dependente da interface?

---

## 🔹 7. Reflexão final

Responder:

- BDD melhora comunicação entre equipe?
- Todo teste deve usar BDD?
- Quando vale a pena usar BDD?
- Como isso ajuda no projeto do grupo?

---

# 📦 Entregável

Formato:

- arquivo Markdown (.md)

Nome:

```text
/aula-12-bdd-automacao-comportamento.md
```

Entrega:

- repositório GitHub do grupo

---

# 📊 Avaliação (Rubrica – Unisenac-RS)

## 🔴 D — Não atingiu

- Cenários incompletos
- Estrutura incorreta
- Automação não executa

## 🟡 C — Parcial

- Cenários pouco claros
- Automação parcial

## 🔵 B — Pleno

- Cenários corretos
- Automação funcional
- Boa separação Given-When-Then

## 🟢 A — Excelência

- Cenários claros
- Boa representação de regras de negócio
- Código organizado
- Automação robusta
- Excelente análise crítica

---

# 💡 Dica final

Para obter conceito A:

- Escrevam cenários pensando no negócio
- Evitem detalhes excessivamente técnicos
- Criem automações legíveis
- Organizem corretamente o projeto
- Pensem na manutenção futura

👉 Mentalidade esperada:

> “Uma pessoa não técnica conseguiria entender o comportamento descrito?”
