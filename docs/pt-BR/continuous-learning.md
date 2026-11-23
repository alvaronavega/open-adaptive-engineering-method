# Aprendizado contínuo (fundação)

## Propósito

OAEM foi feita para evoluir a partir do uso real, não como teoria estática.

Aprendizado contínuo define um loop metodológico que transforma fricções observadas em melhorias reproduzíveis e cobertura de conformidade.

## Loop central

`usar método → observar fricção → reproduzir → classificar → melhorar → adicionar cobertura de regressão/conformidade → publicar versão refinada`

## Categorias de classificação (v0.1)

Usar categorias explícitas para não confundir bug de produto com defeito de método:

- `METHOD_DEFECT`
- `SKILL_DEFECT`
- `ADAPTER_DEFECT`
- `HARNESS_DEFECT`
- `DOCUMENTATION_DEFECT`
- `FALSE_COMPLETION`
- `FALSE_HUMAN_BOUNDARY`
- `MISSING_EVIDENCE`
- `UNNECESSARY_ARTIFACT`
- `CONTEXT_OVERHEAD`
- `CROSS_MACHINE_FAILURE`
- `AGENT_SCOPE_DRIFT`
- `VALIDATION_GAP`

## Intenção da classificação

### Defeito de produto
Problema no sistema/produto sendo desenvolvido.  
Pode exigir uso de OAEM, mas não implica automaticamente que OAEM esteja errada.

### Defeito metodológico
Regra/desenho da própria OAEM que gera fricção recorrente, ambiguidade ou comportamento inseguro.

### Defeito de harness
Comportamento da ferramenta/runtime que compromete portabilidade de execução ou integridade de evidência.

Classificação clara evita correções no lugar errado.

## Qualidade esperada do feedback

Sinais úteis de aprendizado devem incluir:
- contexto conciso de reprodução;
- comportamento observado vs esperado;
- nível de profundidade usado;
- evidência disponível/ausente;
- se fronteira humana foi tratada corretamente;
- fatores cross-machine/harness envolvidos.

## Disciplina de melhoria

Ao alterar OAEM com base em feedback:
1. identificar escopo da mudança metodológica;
2. atualizar primeiro docs canônicos (inglês);
3. atualizar tradução oficial (pt-BR);
4. ajustar expectativas de conformidade quando aplicável;
5. registrar nota de versão/changelog.

## Anti-padrões

- encerrar com “funciona aqui” sem reprodução;
- rotular defeito metodológico como “erro do usuário” sem evidência;
- mudar comportamento sem atualizar contrato do método;
- criar artefato novo que aumenta overhead sem reduzir risco.

## Relação com maturidade de conformidade

No v0.1, conformidade é principalmente fundacional e documental.  
Com evolução, deve migrar para checagens executáveis e regressões que validem o método em múltiplos harnesses.

## Artefatos relacionados

- [Problemas e modos de falha](problems-and-failure-modes.md)
- [Modelo de evidência](evidence-model.md)
- [Portabilidade entre harnesses](harness-portability.md)
- [Política de checkpoint](checkpoint-policy.md)
