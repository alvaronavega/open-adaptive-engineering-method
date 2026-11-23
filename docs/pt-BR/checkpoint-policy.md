# Política de checkpoint (fundação)

## Propósito

A política de checkpoint define quando e por que o OAEM preserva progresso como fronteira local coerente de commit.

Checkpoint não é apenas “salvar andamento”.  
É um ponto de controle vinculado a evidência para rollback, comparação e atribuição de regressão.

## Regra central

Registrar checkpoint de progresso coerente, não de movimentação parcial arbitrária.

Um checkpoint deve representar uma intenção clara com evidência adequada ao nível de profundidade escolhido.

## O que torna um checkpoint válido

Um checkpoint é válido quando todos os critérios abaixo são verdadeiros:

1. A fatia tem intenção clara.
2. A validação focada exigida para aquela fatia passou.
3. Gates determinísticos obrigatórios do nível selecionado não falham.
4. Mudanças não relacionadas foram excluídas.
5. O checkpoint pode ser entendido de forma independente por quem revisar depois.

## Preferência por checkpoints verticais

OAEM é vertical por padrão.  
A política de checkpoint segue essa regra:
- priorizar checkpoint de fatia vertical concluída;
- evitar acumulação horizontal extensa antes do primeiro estado preservável.

## Checkpoints de defeito

Sequência preferida para checkpoint de correção:

`falha observada → reproduzir → menor correção tecnicamente sólida → evidência de regressão → checkpoint`

Evitar agrupar refatorações não relacionadas no mesmo checkpoint de defeito.

## Checkpoint vs autoridade de push/release

Checkpoint e publicação são fronteiras de autoridade diferentes:

- **Checkpoint (local)**: preserva progresso validado.
- **Push/release**: fronteira de autoridade do projeto, podendo exigir aprovação adicional.

Checkpoint local válido não implica autorização automática de publicação.

## Comportamento em gates obrigatórios

Se gates obrigatórios falham no nível escolhido:
- não reportar COMPLETE;
- não registrar checkpoint como fatia concluída;
- continuar correção delimitada ou escalar conforme política.

## Disciplina de staging

Qualidade de checkpoint depende de staging seletivo:
- incluir apenas arquivos ligados à intenção atual;
- excluir alterações sujas não relacionadas;
- evitar staging cego como comportamento padrão.

## Estabilidade histórica

Manter consistência de política de commit daqui para frente, sem reescrever histórico antigo apenas por padronização estética, salvo autorização explícita de governança.

## Artefatos relacionados

- [Política de commit e checkpoint](commit-and-checkpoint-policy.md)
- [Contrato de conclusão](completion-contract.md)
- [Modelo de evidência](evidence-model.md)
