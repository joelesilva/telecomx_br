# Análise de Evasão de Clientes (Churn) - Telecom X

## Propósito da Análise

Este projeto teve como objetivo principal investigar os fatores que levam à evasão de clientes (churn) na Telecom X. Através de uma análise de dados abrangente, buscamos identificar padrões e características dos clientes que cancelam seus serviços, fornecendo insights valiosos para a criação de modelos preditivos e o desenvolvimento de estratégias de retenção eficazes.

## Estrutura do Projeto

```bash
├── TelecomX_BR.ipynb # O notebook principal que contém todo o fluxo de trabalho, desde a coleta de dados até as análises exploratórias e de correlação.
├── TelecomX_Data.json # Dataset utilizado na importação dos dados analizados.
│
├── relatorio_final_churn_com_imagens.pdf # Relatório final em PDF
├── correlation_analysis_summary.pdf # Relatório Análise de Correlação - Telecom X Churn em PDF
│
└── README.md # Documentação deste repositório
```
## Principais Desafios e Soluções

Durante o projeto, enfrentamos e superamos os seguintes desafios:

1.  **Coleta e Normalização de Dados:** Os dados foram obtidos de uma API em formato JSON aninhado. Foi necessário desenvolver um script para carregar e normalizar essas informações em um DataFrame do Pandas, garantindo que todas as variáveis fossem acessíveis para análise.
2.  **Tratamento de Valores Ausentes:** Identificamos valores ausentes críticos na variável alvo (`Churn`) e na variável numérica `Charges.Total`. Para `Churn`, as linhas com valores ausentes foram removidas. Para `Charges.Total`, os valores ausentes (que correspondiam a clientes novos com `tenure` zero) foram imputados com zero, garantindo a integridade dos dados numéricos.
3.  **Padronização e Transformação:** Para otimizar a análise e preparar os dados para futuras modelagens, realizamos a conversão de variáveis categóricas binárias ("Yes"/"No") para formato numérico (1/0) e renomeamos todas as colunas para português, aumentando a clareza e a usabilidade do dataset.

## Insights e Resultados Obtidos

A análise exploratória e de correlação revelou insights cruciais sobre o comportamento de churn na Telecom X:

*   **Taxa de Churn:** Aproximadamente 26.5% dos clientes da Telecom X cancelam seus serviços, indicando um problema significativo de retenção.

*   **Fatores de Risco (Maiores Taxas de Churn):**
    *   **Contratos Mensais:** Clientes com contratos mensais apresentam uma taxa de churn drasticamente maior (>42%) em comparação com contratos anuais ou bienais.
    *   **Clientes Recentes:** O churn é mais prevalente nos primeiros meses de contrato (`Meses_Contrato` tem a correlação negativa mais forte com Churn, -0.352).
    *   **Cobranças Mensais Elevadas:** Clientes com `Cobranca_Mensal` mais alta tendem a cancelar mais (correlação positiva de 0.193).
    *   **Serviço de Fibra Óptica:** Clientes com Fibra Óptica têm uma taxa de churn significativamente maior (>41%) do que aqueles com DSL.
    *   **Método de Pagamento:** O uso de Débito Eletrônico (Electronic check) está associado à maior taxa de churn (>45%).
    *   **Ausência de Serviços Adicionais:** A falta de serviços como Segurança Online e Suporte Técnico está fortemente ligada a maiores taxas de churn.
    *   **Demografia:** Clientes idosos e aqueles sem parceiro(a) ou dependentes também mostram maior risco de churn.

*   **Fatores de Retenção (Menores Taxas de Churn):**
    *   **Contratos de Longo Prazo:** Clientes com contratos de 1 ou 2 anos são significativamente mais leais.
    *   **Maior Tempo de Contrato:** Clientes mais antigos tendem a permanecer.
    *   **Adesão a Serviços Adicionais:** A contratação de serviços como Suporte Técnico e Segurança Online parece aumentar a retenção.

## Conclusões e Recomendações

Com base nos insights, a Telecom X pode adotar as seguintes estratégias para mitigar a evasão de clientes:

1.  **Incentivar Contratos de Longo Prazo:** Criar campanhas e programas de fidelidade para migrar clientes de planos mensais para anuais/bienais, oferecendo benefícios claros.
2.  **Revisar Estratégia de Preços e Valor:** Analisar a precificação da Fibra Óptica e considerar o *bundling* de serviços de valor agregado (Segurança Online, Suporte Técnico) para aumentar o valor percebido, especialmente para clientes com cobranças mensais elevadas.
3.  **Otimizar Métodos de Pagamento:** Investigar as causas da alta taxa de churn associada ao Débito Eletrônico e incentivar métodos de pagamento com menor risco.
4.  **Fortalecer Suporte e Serviços Adicionais:** Promover ativamente os serviços de Segurança Online e Suporte Técnico, destacando seus benefícios, e considerar incluí-los em pacotes ou oferecer períodos de teste.
5.  **Melhorar a Experiência do Cliente Recente:** Reforçar o processo de *onboarding* e monitorar a satisfação nos primeiros meses para intervir proativamente.
6.  **Desenvolver Campanhas de Retenção Segmentadas:** Utilizar os perfis de risco identificados para criar ofertas e comunicações personalizadas.

Essas ações visam não apenas reagir ao churn, mas também construir uma base de clientes mais leal e satisfeita.

## Instruções para Executar o Notebook

ara replicar as análises e explorar o projeto, siga os passos abaixo:

1.  **Clone o Repositório:**
    ```bash
    git clone https://github.com/joelesilva/telecomx_br.git
    cd telecomx_br
    ```
2.  **Abra o Notebook:** Você pode abrir o `TelecomX_BR.ipynb` no Jupyter Notebook, JupyterLab ou Google Colab.
    *   **Jupyter Notebook/Lab:**
        ```bash
        jupyter notebook
        # ou jupyter lab
        ```
        Navegue até o arquivo `.ipynb` e abra-o.
    *   **Google Colab:** Faça o upload do arquivo `TelecomX_BR.ipynb` diretamente para o Google Colab.
3.  **Execute as Células:** Execute as células do notebook sequencialmente para reproduzir todas as etapas da análise.


---

> Para dúvidas ou sugestões, abra uma issue ou entre em contato via e-mail: [joelesilva@gmail.com](mailto:joelesilva@gmail.com).
