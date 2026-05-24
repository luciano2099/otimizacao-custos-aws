# Painel de Controle de Custos AWS (Cost Optimization Dashboard)

**Empresa:** Abstergo Industries  
**Responsável:** Luciano Siviero  
**Data da Última Atualização:** 24 de Maio de 2026  

Este documento mapeia a estrutura, métricas e alarmes configurados no **AWS Budgets** e **AWS Cost Explorer** para o projeto de mitigação de custos imediatos. Ele serve como o blueprint do painel de controle dinâmico para acompanhamento da liderança no repositório.

---

## 📊 1. Resumo de Métricas Chave (KPIs)

| Métrica | Valor Atual (Mensal) | Meta / Projeção | Status | Ação Automatizada |
| :--- | :---: | :---: | :---: | :--- |
| **Gasto Geral de Computação (EC2)** | $1,200.00 | $240.00 | 🟢 Dentro do Esperado | Alocação Spot ativa em 80% dos Workers |
| **Armazenamento de Dados (S3)** | $450.00 | $90.00 | 🟡 Aplicando Políticas | Transição em lote para o Glacier em andamento |
| **Eficiência Financeira Relativa** | 0% Otimizado | **76.1% de Economia** | 🔵 Em evolução | Monitoramento contínuo via Cost Explorer |

---

## 🚨 2. Regras de Negócio & Limites do AWS Budgets

Configuramos **Alarmes Automatizados** que disparam alertas imediatos via e-mail e canais do Slack quando o consumo se comporta de forma anômala:

### 🔴 Alarme 1: Orçamento Geral Mensal (Abstergo-Total-Budget)
- **Limite Fixo:** $435.00 / mês (Soma dos custos otimizados + margem de segurança).
- **Gatilho de Alerta 1:** Dispara ao atingir **80% ($348.00)** do valor previsto (Notificação de atenção).
- **Gatilho de Alerta 2:** Dispara se a **projeção de fim de mês** do Cost Explorer prever que vamos estourar os $435.00 (Ação preventiva).

### 🟠 Alarme 2: Desperdício de Instâncias On-Demand (EC2-OnDemand-Spike)
- **Foco:** Evitar que desenvolvedores subam servidores caros fora do ecossistema Spot por engano.
- **Gatilho:** Se o gasto diário com instâncias On-Demand passar de **$15.00**, um relatório de anomalia é gerado e enviado ao responsável técnico.

---

## ⚙️ 3. Políticas de Ciclo de Vida Automatizadas (S3 Lifecycle JSON)

Para garantir que a **Etapa 3** funcione de forma 100% autônoma (sem ninguém precisar mover arquivo na mão), aplicamos a seguinte política no bucket principal da Abstergo:

```json
{
  "Rules": [
    {
      "ID": "Mover Logs Antigos para Glacier",
      "Status": "Enabled",
      "Filter": {
        "Prefix": "logs/"
      },
      "Transitions": [
        {
          "Days": 30,
          "StorageClass": "GLACIER"
        }
      ],
      "NoncurrentVersionTransitions": [
        {
          "NoncurrentDays": 14,
          "StorageClass": "GLACIER"
        }
      ]
    }
  ]
}



# https://194f8cc6-8b8b-4560-bb13-ad2cfecc817f-00-q4p35wimooaq-ii8rcsxb.worf.replit.dev/


