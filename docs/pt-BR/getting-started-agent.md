# Primeiros passos para agentes de IA (bootstrap inicial)

## Escopo

Este documento define o bootstrap **inicial** de OAEM para agentes de IA.

Ele é propositalmente fundacional e não representa o protocolo executável final detalhado.  
Mecânicas completas de contrato ficam para fases futuras de core contracts.

## Compromissos básicos do agente

Um agente alinhado ao OAEM deve:
- manter comportamento agnóstico de modelo e consciente de harness;
- preservar fronteiras de autoridade humana;
- preferir fechamento vertical de fatias;
- exigir evidência para alegações de conclusão;
- evitar substituir prova determinística por linguagem de confiança.

## Protocolo inicial de bootstrap (v0.1)

### 1) Descobrir autoridades do projeto
Identificar fontes autoritativas, como:
- arquivos de política do repositório;
- fronteiras de segurança/governança;
- regras de escalada humana documentadas;
- restrições de branch/release/publicação.

### 2) Detectar configuração de adoção OAEM (se existir)
Verificar se o projeto já define:
- preferências de profundidade;
- gates de evidência obrigatórios;
- convenções de checkpoint;
- restrições de adapter/harness.

Se não existir, aplicar comportamento padrão de fundação OAEM e declarar suposições.

### 3) Identificar o resultado solicitado
Definir o que precisa ser entregue de forma verificável.

### 4) Classificar mudança por risco/complexidade/incerteza
Classificar com base em impacto, reversibilidade e fronteiras envolvidas.

### 5) Escolher profundidade mínima suficiente
Selecionar Nível 0/1/2/3 com justificativa curta.

### 6) Identificar Skills disponíveis
Usar apenas Skills necessárias para a fatia atual, sem carregar sobrecarga desnecessária.

### 7) Identificar harness ativo e restrições
Mapear:
- ferramentas/comandos disponíveis;
- limites de permissão;
- fronteiras de filesystem/rede;
- semântica de execução.

### 8) Identificar evidência determinística exigida para conclusão
Definir evidência mínima antes de alegar conclusão.

### 9) Identificar fronteiras humanas legítimas
Antes de executar, detectar possíveis pontos obrigatórios de escalada:
- dependência/credencial/segurança/release/operação destrutiva etc.

### 10) Executar verticalmente até satisfazer contrato de conclusão ou atingir fronteira humana real
Fluxo padrão:
`intenção → contrato → implementação mínima entre camadas necessárias → validação focada → integração → evidência → checkpoint → concluído`

Para defeitos:
`falha observada → reproduzir → primeiro contrato quebrado → menor correção tecnicamente sólida → teste de regressão → regressão afetada → evidência → checkpoint`

### 11) Corrigir defeitos delimitados e continuar
Defeitos técnicos comuns não são fronteira humana por padrão.

### 12) Registrar checkpoint de progresso coerente e validado
Preservar avanço validado conforme política do projeto.

### 13) Nunca substituir evidência por confiança do modelo
Se validação determinística é possível, ela é autoritativa.  
Inferência narrativa sozinha não basta para concluir.

## Comportamento de escalada

Se surgir fronteira humana real:
- interromper continuação autônoma;
- declarar claramente a categoria de fronteira;
- apresentar opções/riscos e insumos necessários para decisão;
- não reportar COMPLETE.

## Documentos de fundação relacionados

- [Visão geral da metodologia](methodology-overview.md)
- [Profundidade adaptativa](adaptive-depth.md)
- [Contrato de conclusão](completion-contract.md)
- [Modelo de evidência](evidence-model.md)
- [Fronteiras humanas](human-boundaries.md)
- [Política de checkpoint](checkpoint-policy.md)
