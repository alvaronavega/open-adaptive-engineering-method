# Primeiros passos para pessoas

## Para quem é este guia

Este guia é para engenheiros, líderes e equipes que querem adotar OAEM em trabalho real sem perder autoridade humana.

## O que é OAEM (versão curta)

OAEM é uma metodologia para engenharia de software assistida por IA:
- adaptativa ao risco e ao escopo;
- orientada por evidências;
- agnóstica de modelo;
- agnóstica de harness;
- aplicável de forma incremental.

Ela não substitui julgamento de engenharia.  
Ela organiza como executar com IA de forma mais governável, verificável e reproduzível.

## Autoridade humana preservada

Decisões consequenciais seguem sob autoridade humana, incluindo:
- introdução de dependências;
- uso de credenciais e acesso externo;
- mudanças de postura de segurança;
- operações destrutivas de versionamento;
- decisões de release/deploy;
- trade-offs arquiteturais maiores.

OAEM ajuda agentes a executar trabalho delimitado; não transfere responsabilidade final.

## Como começar sem sobrecarga

Adote o mínimo necessário primeiro e aumente rigor apenas quando o risco pedir.

### Opção A: começar no Nível 0
Use OAEM para:
- correções locais pequenas;
- validação focada;
- checkpoints coerentes.

Objetivo: disciplina de evidência e checkpoint sem peso processual.

### Opção B: consolidar no Nível 1
Adicionar:
- critérios de aceite explícitos;
- regressão focada;
- reportes de conclusão mais claros.

Objetivo: consistência em mudanças de escopo médio.

### Opção C: usar Nível 2/3 com seletividade
Aplicar especificação temporária ou mudança governada apenas quando risco e impacto justificarem.

Objetivo: investir artefato onde reduz risco de fato.

## Sequência prática de adoção

1. Alinhar princípios OAEM (especialmente evidência acima de alegação e vertical por padrão).
2. Escolher um fluxo/time como piloto.
3. Definir evidência mínima por nível de profundidade.
4. Aplicar checkpoints em fatias coerentes.
5. Revisar fricções de forma periódica e classificar defeitos (método/harness/documentação).
6. Expandir adoção apenas quando houver evidência de valor.

## Evidência é definida pelo projeto consumidor

OAEM fornece a estrutura metodológica; cada projeto define os gates determinísticos específicos (testes, build, análise estática, etc.) para seu contexto.

## Uso seguro de autonomia

Autonomia funciona melhor com:
- escopo delimitado;
- fatias verticais curtas;
- validação focada;
- checkpoint frequente;
- fronteiras humanas explícitas.

## Checkpoints reduzem risco

Checkpoints locais de progresso validado melhoram:
- rollback;
- comparação antes/depois;
- atribuição de regressão;
- recuperação após falha de agente.

## Anti-padrões

- exigir adoção total antes de entregar valor;
- aceitar conclusão com linguagem de confiança sem evidência;
- escalar defeitos técnicos comuns como decisão humana;
- acumular diff grande sem checkpoint intermediário;
- misturar mudanças não relacionadas no mesmo commit.

## Sinal de adoção saudável

A adoção está funcionando quando:
- fatias verticais menores passam a fechar com previsibilidade;
- evidência fica atual e reproduzível;
- checkpoints ajudam diagnóstico e recuperação;
- escaladas humanas ficam menos frequentes e mais relevantes.
