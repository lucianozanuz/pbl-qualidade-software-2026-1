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

Os testes unitários foram implementados no arquivo:

👉 `/tests/test_pedido.py`

A implementação da funcionalidade está em:

👉 `/src/pedido.py`

Foram criados testes para:
- Cenário de sucesso (valor acima do mínimo)
- Cenário de erro (valor abaixo do mínimo)
- Cenário de borda (valor exatamente igual ao mínimo)

---

## 🔹 3. Aplicação do TDD

### 🔴 Red (Teste falhando)
- O teste foi criado antes da implementação da função  
- Ao executar, ocorreu erro (função inexistente)  
- Isso confirmou que o teste estava válido e falhando corretamente  

---

### 🟢 Green (Código mínimo)
- Foi implementado o código mínimo necessário para passar no teste  
- A solução inicial foi simplificada e não cobria todos os cenários  

---

### 🔵 Refactor
- O código foi refatorado para atender corretamente as regras de negócio  
- A implementação passou a ser genérica e reutilizável  
- Os testes garantiram que nenhuma funcionalidade foi quebrada  

---

## 🔹 4. Refatoração

### Melhorias realizadas
- Substituição de implementação fixa por lógica real  
- Uso de função de agregação (`sum`)  
- Inclusão de validação de regra de negócio  
- Separação adequada entre código e testes  

---

### Por que foram necessárias
- O código inicial era apenas provisório  
- Não representava corretamente o comportamento esperado  
- Não era reutilizável  

---

### Papel dos testes
- Garantiram segurança na evolução do código  
- Permitiram refatorar sem quebrar funcionalidades  
- Validaram diferentes cenários  

---

## 🔹 5. Execução dos Testes

Execução realizada via terminal com ferramenta de testes (ex: pytest).

Resultados:
- Total de testes: 3  
- Testes que passaram: 3  
- Testes que falharam: 0  

Evidência:
- Execução realizada com sucesso (ver saída no terminal do projeto)

---

## 🔹 6. Reflexão

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
