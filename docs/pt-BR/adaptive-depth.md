# Profundidade adaptativa

## Objetivo

Profundidade adaptativa define quanto rigor de processo e documentação o OAEM exige para cada tipo de mudança.

OAEM evita os dois extremos:
- ausência de estrutura em trabalho de alto risco;
- estrutura pesada em toda mudança trivial.

Regra central: escolher o **menor artefato suficiente** para o risco real.

## Critérios para seleção de profundidade

A escolha deve considerar fatores práticos:
- risco de comportamento incorreto;
- raio de impacto se houver erro;
- sensibilidade arquitetural;
- implicações de segurança;
- incerteza e desconhecidos;
- necessidade de coordenação entre pessoas/times;
- reversibilidade da mudança.

## Modelo de profundidade (v0.1)

### Nível 0 — Direto
Para mudanças locais, de baixo risco e bem compreendidas.

Fluxo:
`intenção → implementação → evidência focada → checkpoint`

Exemplos típicos:
- correção local pequena com causa clara;
- refatoração isolada sem mudança de contrato;
- ajuste de configuração/texto com verificação determinística.

### Nível 1 — Ticket
Para trabalho de escopo médio que exige critérios de aceite explícitos.

Fluxo:
`objetivo → critérios de aceite → implementação vertical → regressão focada → checkpoint`

Exemplos típicos:
- incremento funcional em área conhecida;
- extensão moderada de comportamento envolvendo vários arquivos;
- correção de bug que pede cobertura de regressão e validação de impacto.

### Nível 2 — Especificação temporária
Para mudanças maiores, porém delimitadas, com incerteza relevante.

Fluxo:
`especificação temporária → histórias verticais → loops de implementação → evidência → conclusão → arquivar/aposentar especificação`

Exemplos típicos:
- adição de capacidade significativa com entrega em etapas;
- migração delimitada em subsistema;
- mudança importante que se beneficia de decisões intermediárias explícitas.

### Nível 3 — Mudança governada
Para mudanças de alto risco ou impacto consequencial.

Fluxo:
`artefato de decisão → análise de impacto/risco → plano autorizado → fatias verticais → evidência determinística → gate humano`

Exemplos típicos:
- substituição arquitetural;
- alteração de modelo de segurança;
- mudança de contrato público/API;
- migração de modelo de dados com preocupações de recuperação.

## Vertical por padrão em qualquer nível

Profundidade não é licença para acumular trabalho horizontal em progresso.

Execução padrão em todos os níveis: fatias verticais com resultado verificável de forma independente:
- valor entregue;
- comportamento validado;
- evidência produzida;
- risco reduzido;
- aprendizado registrado.

Trabalho horizontal é permitido apenas por necessidade demonstrada (ver [Visão geral da metodologia](methodology-overview.md)).

## Defeitos também seguem profundidade adaptativa

Correções de defeitos devem usar fatias verticais proporcionais ao risco.

Fluxo preferido de defeito:
`falha observada → reproduzir → primeiro contrato quebrado → menor correção tecnicamente sólida → teste de regressão → regressão afetada → evidência → checkpoint`

Evitar expansão do tipo “já que toquei nesta camada, vou refatorar tudo”.

## Efeitos práticos esperados

Profundidade adaptativa deve reduzir:
- sobrecarga documental;
- inflação de contexto;
- deriva de status;
- descoberta tardia de regressões.

Preservando:
- rastreabilidade quando necessária;
- integridade da evidência;
- clareza de decisão;
- recuperabilidade por checkpoints coerentes.
