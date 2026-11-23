# Problemas e modos de falha

Este documento registra modos de falha recorrentes que motivaram o OAEM.

O objetivo não é rejeitar práticas orientadas por especificação ou por Skills.  
O objetivo é tratar lacunas práticas de governança e execução observadas em desenvolvimento assistido por IA de longa duração.

## 1) Sobrecarga documental sem profundidade adaptativa

### Problema
Abordagens estruturadas/orientadas por especificação trazem valor:
- intenção explícita;
- clareza de planejamento;
- rastreabilidade;
- gates de qualidade.

Mas aplicar a mesma profundidade em toda tarefa pode gerar:
- excesso de artefatos;
- informação duplicada;
- múltiplas fontes concorrentes de verdade;
- deterioração da especificação e deriva de status;
- custo desproporcional de contexto e manutenção.

### Resposta OAEM
Selecionar profundidade adaptativa com base em risco, complexidade, incerteza, escopo e impacto.  
Escolher o menor artefato de engenharia suficiente para o risco real.

---

## 2) Skills sozinhas não são governança completa

### Problema
Skills de engenharia composáveis melhoram execução e reuso, mas não respondem sempre:
- qual Skill deve rodar em cada momento;
- qual rigor é necessário;
- qual evidência é exigida para concluir;
- quando o agente pode parar;
- quando checkpoint é obrigatório;
- quando decisão humana é realmente necessária;
- como manter consistência entre harnesses.

### Resposta OAEM
Combinar práticas composáveis com artefatos explícitos de governança:
- contrato de conclusão;
- modelo de evidência;
- política de checkpoint;
- política de fronteiras humanas;
- contrato de portabilidade entre harnesses.

---

## 3) Agentes param um passo cedo demais

### Problema
Padrão frequente:
1. o agente analisa corretamente;
2. identifica a próxima ação executável;
3. responde “próximo passo: implementar …” em vez de implementar.

### Resposta OAEM
Definir comportamento explícito de loop de execução e contratos de conclusão para que “analisar próximo passo” não seja tratado como conclusão.

---

## 4) Conclusão falsa

### Problema
Padrões observados:
- reportar PASS sem executar validação;
- reutilizar evidência antiga como se fosse atual;
- marcar implementação parcial como completa;
- remover testes alegando cobertura preservada;
- tratar confiança do modelo como prova;
- sobrepor falha determinística com narrativa.

### Resposta OAEM
Regra central OAEM: **alegações de modelo não são evidência de execução**.  
Onde há verificação determinística possível, evidência determinística é autoritativa.

---

## 5) Confusão de fronteira humana

### Problema
Agentes escalam defeitos normais que deveriam ser resolvidos autonomamente (em escopo delimitado), como:
- falhas de teste;
- bugs de parser;
- deriva de documentação;
- defeitos de tooling local;
- regressões delimitadas.

### Resposta OAEM
Distinguir:
- **defeito técnico delimitado** → agente corrige e continua;
- **fronteira humana real** → decisão humana explícita necessária.

Exemplos de fronteira real:
- introdução de nova dependência;
- credenciais/segredos;
- habilitar acesso externo;
- enfraquecimento de política de segurança;
- substituição arquitetural ampla;
- operações destrutivas de controle de versão;
- release/publicação/deploy;
- decisões de negócio/produto.

---

## 6) Falhas de reprodutibilidade entre máquinas

### Problema
Fluxos quebram quando estado necessário não está versionado:
- arquivos obrigatórios não rastreados;
- Skills/adaptadores só locais;
- artefatos gerados tratados como fonte canônica;
- suposições de runtime específicas da máquina;
- scripts/fixtures ausentes;
- paths/config específicos de máquina.

### Resposta OAEM
Exigir conceito de **conformidade em clone limpo**: estado commitado deve bastar para ambiente autorizado novo reconstruir fluxo esperado.

---

## 7) Deriva multiagente / multiharness

### Problema
Harnesses diferentes variam em:
- ferramentas e comandos;
- permissões e semântica de execução;
- formatos de saída;
- limites e hooks.

Sem isolamento explícito, um harness pode mutar configuração de outro sem transparência.

### Resposta OAEM
Usar:
- contrato metodológico comum;
- perfis/adaptadores isolados por harness;
- regra rígida: um harness não deve mutar silenciosamente a configuração de outro.

---

## 8) Execuções autônomas longas sem checkpoints

### Problema
Execuções longas e contínuas podem gerar:
- diffs grandes e pouco revisáveis;
- perda de estados intermediários válidos;
- deriva de escopo;
- diagnóstico de regressão difícil.

### Resposta OAEM
Preferir:
- fatias verticais;
- validação focada;
- checkpoint local;
- continuação controlada.

Em vez de:
- mudança monolítica grande;
- validação única apenas ao final.

---

## Princípio de síntese

OAEM não trata essas ocorrências como falhas isoladas de prompt.  
São modos de falha metodológicos que exigem contratos explícitos, regras de evidência, governança de fronteiras e aprendizado iterativo.
