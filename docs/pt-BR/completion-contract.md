# Contrato de conclusão (fundação)

## Propósito

O contrato de conclusão define quando o trabalho pode ser declarado concluído no OAEM.

Ele evita encerramentos prematuros, como:
- “análise concluída” sem implementação;
- “provavelmente corrigido” sem validação atual;
- alegação de “passou” com evidência antiga.

## Regra central

Uma tarefa só está concluída quando o resultado solicitado **e** a evidência exigida foram satisfeitos.

Confiança de modelo ou narrativa convincente não substitui evidência executável quando há verificação determinística possível.

## Critérios de conclusão de fundação (v0.1)

No mínimo, conclusão deve incluir:

1. **Resultado satisfeito**
   - O comportamento/artefato solicitado existe no escopo esperado.

2. **Evidência produzida**
   - Validação adequada ao risco/profundidade foi executada no contexto atual.

3. **Sem falhas determinísticas bloqueantes**
   - Gates obrigatórios do nível escolhido não estão falhando.

4. **Integridade de escopo preservada**
   - Mudanças não relacionadas não são empacotadas como trabalho concluído.

5. **Pronto para checkpoint**
   - Estado coerente para commit local de checkpoint.

## Conclusão por profundidade adaptativa

| Profundidade | Evidência mínima de conclusão |
|---|---|
| Nível 0 (Direto) | Validação focada comprovando o resultado local |
| Nível 1 (Ticket) | Rastro de critérios de aceite + regressão focada |
| Nível 2 (Especificação temporária) | Evidência por história + rastreio de conclusão contra especificação |
| Nível 3 (Mudança governada) | Gates determinísticos definidos no artefato de decisão + gate humano autorizado |

## Conclusão vertical por padrão

No OAEM, conclusão é vertical por padrão:
- fatia de resultado completa;
- integração necessária;
- validação;
- evidência;
- checkpoint.

Expansão horizontal parcial por camada não é conclusão, salvo escopo explícito e governado.

## Conclusão de defeitos

Para defeitos, a conclusão segue fechamento vertical:

`falha observada → reproduzir → primeiro contrato quebrado → menor correção tecnicamente sólida → teste de regressão → regressão afetada → evidência → checkpoint`

Pular evidência de regressão em defeito reproduzível não é conclusão válida.

## Estados de não conclusão

Não reportar como completo quando houver:
- implementação não aplicada;
- validação obrigatória não executada agora;
- gates obrigatórios falhando;
- apenas raciocínio narrativo do modelo;
- evidência de estado anterior não equivalente;
- fronteira humana pendente que bloqueia continuidade autorizada.

## Estados de resultado de conclusão

Para a fundação, OAEM diferencia ao menos:
- `IMPLEMENTED`
- `VALIDATED`
- `HUMAN_REVIEW_REQUIRED`
- `BLOCKED`
- `DEFERRED`
- `PARTIAL`

## Relação com outros artefatos OAEM

- [Modelo de evidência](evidence-model.md): classes de evidência e confiabilidade.
- [Política de checkpoint](checkpoint-policy.md): quando preservar progresso validado.
- [Fronteiras humanas](human-boundaries.md): quando escalar obrigatoriamente.
- [Profundidade adaptativa](adaptive-depth.md): rigor mínimo por risco.
