# Estratégia Inicial de Testes – LocalEats

## 1. Funcionalidades
- Login
- Funcionalidade 2
- Funcionalidade 3
- Funcionalidade 4
- Funcionalidade 5
- Funcionalidade 6

---

## 2. Níveis de Teste

### Login
- Unitário: validação de senha
- Integração: comunicação com banco
- Sistema: fluxo completo de login
- Aceitação: usuário consegue acessar

---

## 3. Prioridades e Riscos

Alta prioridade:
- Busca (principal funcionalidade)
- Login (acesso ao sistema)

Justificativa:
Falhas nessas áreas impedem o uso da plataforma.

---

## 4. Pirâmide de Testes

- Maior foco: testes unitários (validação de regras)
- Médio foco: integração
- Menor foco: testes de sistema

Justificativa:
Testes unitários são mais rápidos e baratos.

---

## 5. Testes em Produção

- Uso de Canary Release
- Aplicar em novas funcionalidades

Justificativa:
Reduz risco de impacto para todos os usuários.
