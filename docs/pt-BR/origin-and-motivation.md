# Origem e motivação

## Por que OAEM existe

OAEM surgiu de fricções práticas recorrentes em trabalhos longos de engenharia de software assistida por IA.

A motivação inicial não foi criar mais uma coleção de prompts nem mais um wrapper de agente.  
Foi reduzir lacunas recorrentes entre:
- intenção de engenharia estruturada;
- comportamento real de execução dos agentes;
- evidências confiáveis de conclusão;
- reprodutibilidade entre máquinas e harnesses;
- custo operacional sustentável do fluxo.

## Problema fundador

Times e profissionais individuais conseguem bons resultados com abordagens orientadas por especificação e por Skills.  
Mas, com o tempo, padrões de falha aparecem quando a governança metodológica é incompleta.

OAEM responde a isso com um contrato metodológico:
- adaptativo ao risco e à complexidade;
- orientado por evidências;
- agnóstico de modelo;
- agnóstico de harness;
- explícito sobre fronteiras de decisão humana;
- iterativo e evolutivo a partir do uso real.

## Categorias de fricção prática

OAEM foi moldado por padrões concretos observados em engenharia real:

1. Profundidade documental estática para riscos dinâmicos.
2. Skills melhorando execução, mas sem governança completa.
3. Agentes parando um passo antes da implementação.
4. Alegações de conclusão sem evidência determinística atual.
5. Decisões de fronteira humana aplicadas de forma inconsistente.
6. Fluxos que não se reproduzem em ambientes limpos.
7. Deriva entre múltiplos agentes e múltiplos harnesses.
8. Execuções autônomas longas sem checkpoints revisáveis.

Detalhamento em:
- [Problemas e modos de falha](problems-and-failure-modes.md)

## Intenção de design para v0.1

OAEM v0.1 estabelece fundação, não padrão final.

Prioriza:
- clareza de identidade e escopo;
- modos de falha documentados;
- baseline de profundidade adaptativa;
- princípios de governança;
- política de idioma e tradução;
- estrutura preparada para contratos, adaptadores, conformidade e evolução do método.

## Não objetivos na fase de fundação

OAEM v0.1 não busca:
- entregar implementações completas de adaptadores para todos os harnesses;
- prender usuários a modelo, IDE, linguagem ou stack de CI específicos;
- substituir padrões de engenharia próprios de cada projeto;
- declarar desempenho comprovado em escala industrial.

## Filosofia de evolução do método

OAEM deve evoluir em ciclo:
1. usar o método em trabalho real;
2. capturar fricção com contexto reproduzível;
3. classificar defeito de método vs harness vs implementação;
4. melhorar artefatos metodológicos;
5. adicionar cobertura de conformidade/regressão;
6. publicar versão refinada.

Assim OAEM se mantém prático, e não apenas teórico.
