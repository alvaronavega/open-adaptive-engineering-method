# Fronteiras humanas (fundação)

## Propósito

Fronteiras humanas definem quando a execução autônoma deve parar e solicitar decisão explícita de autoridade humana.

Isso evita duas falhas comuns:
- escalonamento desnecessário de defeitos técnicos delimitados;
- execução não autorizada de decisões consequenciais.

## Distinção central

OAEM separa:

1. **Defeito técnico delimitado**  
   O agente deve corrigir e continuar dentro do escopo aprovado.

2. **Fronteira humana real**  
   O agente deve parar e obter autorização explícita antes de seguir.

## Defeitos delimitados (seguir autonomamente)

Exemplos:
- falha de teste causada pela mudança atual;
- erro de parser/tipo/formatação no escopo local;
- deriva documental causada pelas edições em andamento;
- regressão delimitada em superfícies diretamente afetadas;
- defeito de script/tooling local com correção segura.

Regra: se a correção é tecnicamente delimitada e não cruza fronteira de autoridade, corrigir, verificar e continuar.

## Fronteiras humanas reais (escalar obrigatoriamente)

Exemplos:
- adicionar nova dependência ou nova fonte de pacote;
- uso de credenciais/segredos ou acesso privilegiado;
- habilitar novo acesso externo (rede/sistema);
- enfraquecer política ou controle de segurança;
- operação destrutiva de versionamento;
- substituição arquitetural ampla fora do escopo autorizado;
- ações de release/publicação/deploy;
- decisões de negócio/produto;
- decisões legais/compliance quando aplicável.

Regra: parar, declarar a categoria de fronteira e solicitar decisão explícita.

## Conteúdo esperado na escalada

Quando escalada for necessária, incluir:
- categoria da fronteira;
- por que a continuação cruza autoridade;
- opções com riscos e consequências;
- recomendação com justificativa;
- mínimo necessário de informação para decisão.

## Anti-padrões

Não escalar por:
- “pode ser difícil”;
- “o teste falhou uma vez”;
- “encontrei um bug de implementação”;
- “a documentação precisa ser ajustada”.

Esses casos são engenharia normal, salvo quando cruzam fronteira real.

## Relação com conclusão e evidência

Se uma fronteira humana bloqueia continuação:
- não reportar COMPLETE;
- reportar status de fronteira com clareza;
- preservar progresso validado em checkpoint delimitado se política permitir.

Ver também:
- [Contrato de conclusão](completion-contract.md)
- [Modelo de evidência](evidence-model.md)
- [Segurança e fronteiras de governança](../../SECURITY.md)
