# Primeiros passos

## Escopo

Esta é a autoridade canônica de onboarding da OAEM Foundation v0.1.

Ela oferece duas rotas concisas:
- **Para Pessoas**
- **Para Agentes de IA**

## Para Pessoas

### 1) Entender o escopo da OAEM
A OAEM é um método para governar trabalho de engenharia assistida por IA com profundidade adaptativa e conclusão orientada por evidências.

### 2) Classificar a mudança
Avaliar risco, complexidade, incerteza e impacto.

### 3) Escolher a profundidade mínima suficiente
Selecionar o menor nível (0–3) que cubra a necessidade com segurança.

### 4) Adotar de forma incremental
Não esperar rollout completo do método. Começar por fatias delimitadas e aumentar rigor só quando o risco exigir.

### 5) Definir evidência determinística
O projeto consumidor define a evidência concreta de conclusão (testes/build/análise estática/segurança conforme aplicável).

### 6) Preservar autoridade humana
Decisões consequenciais permanecem sob autorização humana (dependências, credenciais, acesso externo, enfraquecimento de segurança, operações destrutivas, release/publicação/deploy, decisões de negócio/jurídico).

### 7) Usar checkpoints para reduzir risco
Preferir:
`fatia vertical → validação focada → checkpoint local → continuar`

## Para Agentes de IA (bootstrap de fundação)

Seguir esta sequência de alto nível:

1. descobrir autoridades do projeto;
2. detectar configuração de adoção OAEM (se existir);
3. identificar resultado solicitado;
4. classificar risco/complexidade/incerteza;
5. escolher profundidade mínima suficiente;
6. identificar Skills disponíveis;
7. identificar harness ativa e restrições;
8. identificar evidência determinística exigida;
9. identificar fronteiras humanas legítimas;
10. executar verticalmente até satisfazer o contrato de conclusão ou atingir fronteira humana real;
11. corrigir defeitos delimitados e continuar;
12. registrar checkpoint de progresso coerente validado;
13. nunca substituir evidência determinística por confiança do modelo.

## Progressive Requirement Discovery (conceito de Skill futura)

O roadmap da OAEM mantém o conceito futuro de `grill-requirement` baseado em descoberta progressiva de requisitos:

`pergunta → resposta → atualizar entendimento → escolher próxima pergunta`

Regra canônica:
**Perguntar apenas enquanto a resposta puder alterar materialmente uma decisão de engenharia.**

Não deve ser um questionário fixo.

## Autoridades canônicas relacionadas

- [Metodologia](methodology.md)
- [Governança](governance.md)
- [Inspirações e autor](inspirations-and-author.md)
