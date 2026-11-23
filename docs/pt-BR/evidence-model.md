# Modelo de evidência (fundação)

## Propósito

O modelo de evidência do OAEM define como alegações de conclusão são sustentadas.

Ele distingue:
- qualidade da alegação (o quanto a narrativa parece convincente);
- qualidade da evidência (o que realmente foi executado e observado).

Regra central: quando verificação determinística existe, evidência determinística é autoritativa.

## Classes de evidência (v0.1)

| Classe | Descrição | Confiabilidade |
|---|---|---|
| Evidência determinística de execução | Saída repetível de comando/verificação ligada ao estado atual | Mais alta |
| Evidência de estado de artefato | Diff/arquivo/estado concreto provando que o resultado existe | Alta, quando rastreável |
| Evidência de reprodução | Passos de reprodução e comportamento antes/depois comprovando correção | Alta para defeitos |
| Evidência exploratória | Observações manuais/heurísticas sem replay determinístico | Útil, porém limitada |
| Alegação apenas de modelo | Afirmação narrativa sem prova executável | Insuficiente quando há verificação determinística possível |

## Evidência mínima por profundidade

| Profundidade | Evidência mínima esperada |
|---|---|
| Nível 0 | Verificação determinística focada + confirmação de estado |
| Nível 1 | Cobertura dos critérios de aceite + regressão focada |
| Nível 2 | Mapa de evidência por história + rastreio de conclusão da especificação temporária |
| Nível 3 | Gates determinísticos definidos por decisão + registro de gate humano |

## Atualidade da evidência

A evidência precisa corresponder ao estado candidato atual.

Padrões inválidos:
- reutilizar saída antiga após mudança de estado;
- reportar “pass” de branch/ambiente diferente sem equivalência;
- declarar comportamento preservado sem rerun quando superfícies afetadas mudaram.

## Evidência para defeitos

Evidência preferida em defeitos:
1. falha observada com contexto reproduzível;
2. correção aplicada no primeiro contrato quebrado;
3. teste/verificação de regressão demonstrando fechamento;
4. confirmação da regressão em superfície afetada;
5. rastreabilidade em checkpoint.

## Embalagem de evidência no reporte

Ao reportar conclusão, incluir:
- comando/verificação executado;
- resultado pass/fail;
- saída-chave ou resumo;
- escopo coberto por aquela verificação;
- superfícies conhecidas não cobertas.

## Relação com contrato de conclusão

O contrato de conclusão usa este modelo para decidir se conclusão é autorizada:
- nenhum gate determinístico obrigatório em falha;
- sem “upgrade” silencioso de inferência para evidência por linguagem de confiança.

Ver também:
- [Contrato de conclusão](completion-contract.md)
- [Política de checkpoint](checkpoint-policy.md)
- [Aprendizado contínuo](continuous-learning.md)
