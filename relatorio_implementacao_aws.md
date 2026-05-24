# RELATÓRIO DE IMPLEMENTAÇÃO DE SERVIÇOS AWS

**Data:** 24 de Maio de 2026  
**Empresa:** Abstergo Industries  
**Responsável:** Luciano Siviero  

## Introdução
Este relatório apresenta as ferramentas que escolhi para implementar na Abstergo Industries. O foco principal do projeto foi selecionar 3 serviços da AWS que tragam uma redução de custos imediata e prática para a nossa infraestrutura.

## Descrição do Projeto
Dividi a estratégia de otimização em 3 etapas fundamentais, focando o monitoramento de gastos, o custo de processamento e o armazenamento de arquivos. Abaixo estão os detalhes de cada serviço:

### Etapa 1: Monitoramento e Controle Financeiro
- **Nome da ferramenta:** AWS Budgets / Cost Explorer
- **Foco da ferramenta:** Visibilidade de gastos e alertas de orçamento.
- **Descrição de caso de uso:** Configuramos a ferramenta para acompanhar os custos diários e disparar alertas automáticos caso o consumo ultrapasse o limite que definimos. Isso evita surpresas na fatura no final do mês.

### Etapa 2: Otimização de Processamento (Servidores)
- **Nome da ferramenta:** Amazon EC2 Spot Instances
- **Foco da ferramenta:** Redução de custo em capacidade computacional.
- **Descrição de caso de uso:** Passamos a utilizar instâncias Spot para processamentos pesados e tarefas em lote que podem sofrer interrupções. Como o desconto chega a até 90% em comparação ao preço normal, o impacto na redução de custos é imediato.

### Etapa 3: Gestão Inteligente de Armazenamento
- **Nome da ferramenta:** Amazon S3 Lifecycle Policies
- **Foco da ferramenta:** Ciclo de vida de arquivos e armazenamento de baixo custo.
- **Descrição de caso de uso:** Criamos regras automáticas para mover arquivos antigos ou pouco acessados para o Glacier, que é uma camada de armazenamento bem mais barata. O processo roda sozinho, sem exigir trabalho manual da equipe.

## Conclusão
Com a ativação dessas três ferramentas na Abstergo Industries, a expectativa é cortar os gastos desnecessários de nuvem logo de cara e dar mais previsibilidade para o bolso da empresa. O ideal agora é manter o acompanhamento desses painéis e continuar monitorando os recursos para garantir que a infraestrutura rode sempre enxuta.

## Anexos
- Planilha de projeção de custos (AWS Pricing Calculator)
- Painel de controle de custos configurado

**Responsável pelo Projeto:** Luciano Siviero
