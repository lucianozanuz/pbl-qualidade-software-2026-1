# Aula 12 – BDD e Automação Orientada a Comportamento
# Exemplo de Entrega PBL – LocalEats

## 👥 Integrantes

- Integrante 1
- Integrante 2
- Integrante 3

---

# 🔹 1. Fluxo escolhido

## Integrante: Nome do(a) aluno(a)

### Fluxo
Histórico de pedidos

### Objetivo
Validar se os pedidos realizados pelo usuário são exibidos corretamente.

---

# 🔹 2. Cenários BDD

## Arquivo

```text
features/historico_pedidos.feature
```

## Conteúdo

```gherkin
Feature: Histórico de pedidos

  Scenario: Visualizar pedidos realizados
    Given que o usuário acessa a página de pedidos
    When visualizar o histórico de transações
    Then o sistema deve exibir os pedidos cadastrados

  Scenario: Validar valor total do pedido
    Given que o usuário acessa a página de pedidos
    When visualizar um pedido realizado
    Then o sistema deve exibir o valor total do pedido
```

---

# 🔹 3. Automação com pytest-bdd

## Estrutura do projeto

```text
projeto/
│
├── features/
│   └── historico_pedidos.feature
│
├── tests/
│   └── test_historico_pedidos.py
│
├── evidencias/
│
└── README.md
```

---

## Arquivo

```text
tests/test_historico_pedidos.py
```

## Código

```python
from pytest_bdd import scenarios, given, when, then

scenarios('../features/historico_pedidos.feature')


@given('que o usuário acessa a página de pedidos')
def acessar_pagina(page):
    page.goto('https://local-eats-unisenac.vercel.app/static/orders.html')


@when('visualizar o histórico de transações')
def visualizar_historico(page):
    page.locator('text=Histórico de Transações').is_visible()


@when('visualizar um pedido realizado')
def visualizar_pedido(page):
    page.locator('text=Pedido #1').is_visible()


@then('o sistema deve exibir os pedidos cadastrados')
def validar_pedidos(page):
    assert page.locator('text=Pedido #1').is_visible()


@then('o sistema deve exibir o valor total do pedido')
def validar_total(page):
    assert page.locator('text=R$ 105.98').is_visible()
```

---

# 🔹 4. Execução dos testes

## Comando executado

```bash
pytest -v
```

---

## Resultado

```text
=================== test session starts ===================

2 passed in 5.32s

==========================================================
```

---

# 🔹 5. Evidências

## Print da execução

```text
evidencias/
  execucao-testes.png
```

## Print da aplicação

```text
evidencias/
  historico-pedidos.png
```

---

# 🔹 6. Análise crítica

## O cenário ficou legível?

Sim. A estrutura Given-When-Then ajudou a entender claramente o comportamento esperado.

---

## O BDD ajudou a entender o comportamento?

Sim. O cenário ficou compreensível mesmo para pessoas sem conhecimento técnico.

---

## O teste ficou robusto?

Parcialmente. Alguns seletores dependem diretamente do texto exibido na tela.

---

## Quais dificuldades surgiram?

- Identificar seletores estáveis
- Estruturar corretamente os steps
- Entender integração entre pytest-bdd e Playwright

---

## O teste ficou dependente da interface?

Sim. Mudanças no frontend podem quebrar alguns seletores.

---

# 🔹 7. Reflexão final

## BDD melhora comunicação entre equipe?

Sim. O comportamento do sistema ficou mais claro para QA, desenvolvimento e negócio.

---

## Todo teste deve usar BDD?

Não. BDD deve ser usado principalmente em fluxos importantes do negócio.

---

## Quando vale a pena usar BDD?

Quando o comportamento do sistema precisa ser documentado de forma clara e colaborativa.

---

## Como isso ajuda no projeto do grupo?

Ajuda a transformar requisitos em testes automatizados compreensíveis e organizados.

---

# 📦 Repositório GitHub

```text
https://github.com/grupo-exemplo/local-eats-bdd
```

---

# ✅ Conclusão

A atividade permitiu compreender:

- escrita de cenários BDD
- automação orientada a comportamento
- integração entre pytest-bdd e Playwright
- importância da legibilidade dos testes
- manutenção de automações de frontend
