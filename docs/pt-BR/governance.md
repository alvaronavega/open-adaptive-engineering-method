# Governança (Canônica)

## Escopo

Esta é a autoridade canônica de governança da OAEM Foundation v0.1.

Ela consolida expectativas duráveis de política para:
- autoridade de conclusão e evidência;
- disciplina de commit/checkpoint;
- fronteiras de autoridade humana;
- política de idioma e tradução;
- isolamento entre harnesses;
- sinalização de maturidade.

## Autoridade de conclusão e evidência

Conclusão é contratual, não retórica.

Regras:
- “implementado” não é “concluído” por padrão;
- onde existe verificação determinística, evidência determinística é autoritativa;
- confiança do modelo não sobrepõe falha determinística;
- estado de conclusão deve corresponder à evidência disponível.

Estados de conclusão na fundação:
- `IMPLEMENTED`
- `VALIDATED`
- `HUMAN_REVIEW_REQUIRED`
- `BLOCKED`
- `DEFERRED`
- `PARTIAL`

## Política de commit e checkpoint

### Regras de commit
- uma intenção coerente por commit;
- preferência por fatias verticais em vez de varreduras horizontais amplas;
- staging seletivo em vez de staging cego;
- mudanças sujas não relacionadas devem ficar fora de commits em escopo;
- falha em gates obrigatórios impede status COMPLETE;
- linguagem de commit técnico deve manter consistência em inglês;
- commit de checkpoint não implica autoridade de push/release;
- não reescrever commits históricos apenas para normalização estética.

### Regras de checkpoint
Registrar checkpoint quando todos forem verdadeiros:
1. a intenção da fatia é coerente;
2. a validação focada obrigatória passou;
3. os gates obrigatórios de profundidade não falham;
4. o diff staged corresponde ao escopo declarado;
5. o checkpoint melhora rollback/comparação/atribuição de regressão.

## Fronteiras de autoridade humana

Defeitos técnicos delimitados devem ser corrigidos e a execução deve continuar.

Escalada é obrigatória para fronteiras consequenciais (por exemplo):
- novas dependências;
- credenciais/segredos;
- habilitação de acesso externo;
- enfraquecimento de política de segurança;
- operações destrutivas;
- release/publicação/deploy;
- decisões de negócio/produto/jurídico/compliance.

## Política de idioma e tradução

- Inglês é a fonte técnica canônica.
- pt-BR é tradução oficial de primeira classe.
- A topologia EN/PT-BR deve permanecer equivalente.
- Deriva de tradução deve ser detectável via relação explícita fonte/tradução, sem mecanismo pesado de tradução no v0.1.

## Política de isolamento entre harnesses

O núcleo OAEM permanece independente de detalhes de provedor/runtime.

Invariante crítica:
**Um harness não deve mutar silenciosamente a configuração de outro harness.**

Perfis de adaptador podem variar por harness, mas devem preservar invariantes centrais da OAEM.

## Maturidade e sinalização de versão

OAEM Foundation v0.1 é experimental e inicial.

Regra canônica de maturidade:
**Números de versão representam maturidade demonstrada, não aparência de maturidade.**

Mudanças breaking são esperadas antes da versão 1.0.

## Autoridades relacionadas

- [Metodologia](methodology.md)
- [Primeiros passos](getting-started.md)
- [Inspirações e autor](inspirations-and-author.md)
- [ROADMAP](../../ROADMAP.md)
- [SECURITY](../../SECURITY.md)
