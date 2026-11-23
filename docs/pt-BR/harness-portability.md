# Portabilidade entre harnesses (fundação)

## Propósito

OAEM é agnóstica de harness no núcleo metodológico.

Portabilidade entre harnesses define como OAEM mantém consistência entre diferentes runtimes de agente sem forçar configuração única universal.

## Regra central

Usar:
- um contrato metodológico compartilhado;

mais:
- adaptadores/perfis isolados por harness.

Um harness não deve mutar silenciosamente a configuração de outro harness.

## Por que isso importa

Harnesses diferentes variam em:
- ferramentas e superfícies de comando;
- modelo de permissões;
- formato/verbosidade de saída;
- timeout/retry;
- restrições de filesystem e sandbox;
- semântica de hooks e automação.

Sem isolamento explícito, deriva cross-harness enfraquece reprodutibilidade e confiança.

## Modelo de portabilidade OAEM (v0.1)

1. **Núcleo do método permanece estável**
   - Princípios, regras de evidência, lógica de conclusão e fronteiras humanas permanecem no nível do método.

2. **Camada de adaptador mapeia comportamento do harness**
   - Perfis de adaptador descrevem detalhes de execução específicos de harness preservando a intenção do método.

3. **Conformidade valida equivalência**
   - Harnesses diferentes devem alcançar resultados equivalentes de conclusão/evidência para tarefas equivalentes.

4. **Fronteiras de mutação são explícitas**
   - Configuração local específica de um harness não deve ser reescrita automaticamente por fluxo de outro harness.

## Invariantes de portabilidade

A portabilidade deve preservar ao menos:
- comportamento de profundidade adaptativa;
- execução vertical por padrão;
- regra de evidência acima de alegação;
- requisitos de escalada em fronteiras humanas;
- disciplina de checkpoint.

Se esses invariantes quebram, a portabilidade se degrada mesmo com saída superficialmente parecida.

## Perspectiva de clone limpo

Portabilidade entre harnesses deve ser analisada com suposição de clone limpo:
- ativos obrigatórios versionados no repositório;
- scripts/config necessários documentados;
- ausência de estado local oculto para operação básica.

Ver [Aprendizado contínuo](continuous-learning.md) para classificação de falhas entre máquinas.

## Anti-padrões

- embutir premissas específicas de harness no núcleo OAEM;
- gerar adaptadores sem rastreabilidade em controle de versão;
- reescrever perfis de outro ecossistema de harness silenciosamente;
- alegar portabilidade sem evidência de conformidade.

## Arquitetura de referência

```text
NÚCLEO OAEM
    ├─ Skills
    ├─ Contratos
    ├─ Templates
    ├─ Modelo de evidência
    ├─ Modelo de conclusão
    ├─ Política de checkpoint
    └─ Adaptadores
        ├─ Genérico
        ├─ Ralph
        ├─ Axet
        ├─ Codex
        ├─ Claude
        ├─ Copilot
        ├─ Gemini
        └─ Harnesses futuros
```

O núcleo OAEM não define detalhes específicos de provedor, modelo ou executor.

## Artefatos relacionados

- [Visão geral da metodologia](methodology-overview.md)
- [Contrato de conclusão](completion-contract.md)
- [Modelo de evidência](evidence-model.md)
- [Aprendizado contínuo](continuous-learning.md)
