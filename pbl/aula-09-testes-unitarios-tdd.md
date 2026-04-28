# Aula 9 – Testes Unitários e TDD

## 👥 Integrantes
- Nome 1
- Nome 2
- Nome 3

---

## 📁 Estrutura do Projeto

.
├── src/  
│   └── pedido.py  
└── tests/  
      └── test_pedido.py

---

## 🔹 1. Funcionalidade escolhida

### Funcionalidade
Cálculo do total do pedido com validação de valor mínimo

### Descrição
A funcionalidade soma os valores dos itens de um pedido e valida se o total atinge o valor mínimo exigido pelo restaurante.

### Problema que resolve
Evita que pedidos com valor abaixo do mínimo sejam processados, garantindo consistência nas regras de negócio.

### Importância
Essa é uma regra central do sistema, pois impacta diretamente o fluxo de compra.

### Regras de negócio
- O total é a soma dos preços dos itens  
- O pedido deve atingir o valor mínimo  
- Caso não atinja, deve gerar erro  

---

## 🔹 2. Testes Unitários

Os testes estão implementados em:

👉 `/tests/test_pedido.py`  
A funcionalidade está em:  
👉 `/src/pedido.py`

---

### 🧪 Teste 1 – Cálculo com valor acima do mínimo

#### 🎯 Cenário
Pedido com total maior que o valor mínimo

#### 🔴 Red
- O teste foi escrito antes da implementação  
- Falhou devido à função inexistente  

#### 🟢 Green
- Implementado retorno fixo para fazer o teste passar  

#### 🔵 Refactor
- Implementado cálculo real com `sum()`  
- Adicionada validação de valor mínimo  

#### 🔧 Refatoração
- Código passou de fixo para dinâmico  
- Melhor legibilidade e reutilização  

#### ▶️ Execução
- Resultado: Passou  

---

### 🧪 Teste 2 – Pedido abaixo do valor mínimo

#### 🎯 Cenário
Pedido com total menor que o valor mínimo

#### 🔴 Red
- Teste criado esperando erro  
- Falhou inicialmente  

#### 🟢 Green
- Adicionada verificação de valor mínimo  
- Lançamento de exceção implementado  

#### 🔵 Refactor
- Mensagem de erro padronizada  
- Código reorganizado  

#### 🔧 Refatoração
- Melhoria na clareza da regra de negócio  
- Tratamento explícito de erro  

#### ▶️ Execução
- Resultado: Passou  

---

### 🧪 Teste 3 – Valor exatamente igual ao mínimo

#### 🎯 Cenário
Pedido com total igual ao valor mínimo

#### 🔴 Red
- Teste criado para validar caso de borda  
- Inicialmente falhou  

#### 🟢 Green
- Ajuste na condição (`<` ao invés de `<=`)  

#### 🔵 Refactor
- Código ajustado para tratar corretamente borda  

#### 🔧 Refatoração
- Correção de regra de negócio  
- Garantia de comportamento esperado  

#### ▶️ Execução
- Resultado: Passou  

---

## 🔹 3. Reflexão

### Foi difícil escrever testes antes do código?
Sim, pois exige mudança de mentalidade.

---

### O TDD ajudou no desenvolvimento?
Sim, ajudou a estruturar melhor a lógica antes da implementação.

---

### Os testes aumentaram a confiança no código?
Sim, pois qualquer erro pode ser detectado rapidamente.

---

### O que melhorariam?
- Cobrir mais cenários  
- Melhor organização dos testes  

---

### Como isso ajuda no projeto?
Permite evoluir o sistema com mais segurança e qualidade.
