# Política de commit e checkpoint (fundação)

## Propósito

Este documento diferencia:

- **Política de commit**: como a intenção coerente de mudança é representada no histórico Git.
- **Política de checkpoint**: quando há evidência suficiente para preservar progresso validado como commit.

As duas são necessárias para loops de engenharia autônomos ou semiautônomos confiáveis.

## Nota de origem das convenções

Nesta etapa, o ambiente local ofereceu apenas histórico mínimo deste repositório.  
Nenhum conteúdo externo foi importado como dependência.  
As regras abaixo refletem princípios da fundação OAEM e restrições explícitas desta fundação.

## Política de commit (v0.1)

### 1) Uma intenção coerente por commit
Cada commit deve representar uma intenção de engenharia compreensível.  
Evitar misturar intenções não relacionadas.

### 2) Preferência por fatias verticais
Commit padrão deve fechar resultado vertical (comportamento + evidência), e não varredura horizontal ampla por camada.

### 3) Evidência focada antes do checkpoint de conclusão
Commit marcado como trabalho concluído deve conter evidência adequada ao nível selecionado.

### 4) Gates obrigatórios em falha impedem status COMPLETE
Com gate obrigatório em falha, não declarar conclusão; continuar correção delimitada ou escalar.

### 5) Staging seletivo em vez de staging cego
Preferir staging curado (`git add <paths>`), evitando `git add -A` como padrão em worktree sujo.

### 6) Mudanças sujas não relacionadas ficam de fora
Alterações fora do escopo devem permanecer fora do commit, salvo justificativa explícita.

### 7) Push/release é fronteira de autoridade separada
Criar commit local não implica autorização de push, release ou deploy.

### 8) Consistência futura em mensagens técnicas de commit
Usar inglês consistente em commits técnicos futuros para portabilidade histórica.

### 9) Commits históricos não são reescritos só por estética
Preservar integridade histórica, salvo autorização explícita de governança para reescrita.

## Política de checkpoint (v0.1)

Registrar checkpoint quando todos forem verdadeiros:
1. intenção da fatia é coerente;
2. validação focada obrigatória passou;
3. gates obrigatórios da profundidade não falham;
4. diff staged corresponde ao escopo declarado;
5. checkpoint melhora rollback/comparação/atribuição de regressão.

## Por que checkpoints importam

Checkpoints melhoram:
- segurança de rollback;
- comparação antes/depois;
- atribuição de regressões;
- confiança em execuções autônomas longas.

## Permissão de checkpoint local autônomo

A política do projeto pode autorizar checkpoints locais autônomos para fatias validadas.  
Publicação continua sendo etapa separada de autoridade.

## Anti-padrões

- commits gigantes com intenções misturadas;
- “checkpoint” sem evidência;
- agregação oportunista de mudanças não relacionadas;
- linguagem de confiança em commit com gates em falha.

## Artefatos relacionados

- [Política de checkpoint](checkpoint-policy.md)
- [Contrato de conclusão](completion-contract.md)
- [Modelo de evidência](evidence-model.md)
- [Fronteiras humanas](human-boundaries.md)
