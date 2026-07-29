# 📚 Miniguia de Estudos: Da Contabilidade Tradicional ao Power BI & IA

> **Projeto prático desenvolvido com suporte do Google NotebookLM** para estruturação de conhecimento, engenharia de prompt e análise orientada a dados no setor financeiro/contábil.

---

## 🎯 1. Contexto e Objetivos

### Contexto
O mercado contábil e financeiro passa por uma transformação acelerada. O profissional moderno precisa unir a **rigidez conceitual da contabilidade** (débito/crédito, regimes, normas) à **automação e análise preditiva** via planilhas avançadas, *Business Intelligence* (Power BI) e Inteligência Artificial.

### Objetivos de Estudo
* Criar uma base conceitual sólida em Contabilidade Geral e Estruturas Societárias.
* Dominar técnicas avançadas de modelagem e automação de planilhas no Excel.
* Entender o fluxo de ETL (Extract, Transform, Load) e modelagem em Linguagem M no Power BI.
* Aplicar ferramentas de Inteligência Artificial para análise tributária e geração de relatórios estratégicos.

---

## 📑 2. Curadoria de Fontes

Para alimentar o **NotebookLM** e garantir respostas precisas sem alucinações, foram selecionadas as seguintes fontes abertas e materiais de apoio:

1. 📄 **[PDF] Introdução à Contabilidade Geral e Estrutura das NBCs**
   * *Descrição:* Material cobrindo mecanismos de débito/crédito, plano de contas e regimes contábeis.
   * *Localização:* `fontes/introducao-contabilidade.pdf`
2. 🔗 **[Link/Artigo] Guia de Automação de Planilhas e Validação Dinâmica no Excel**
   * *Descrição:* Documentação técnica detalhando o uso das funções `DESLOC` e `CONT.VALORES`.
3. 📄 **[PDF] Documentação do Power Query e Introdução à Linguagem M**
   * *Descrição:* Manual dos 7 pilares do Power BI, dependência de passos no ETL e otimização de dados.
   * *Localização:* `fontes/guia-powerquery-m.pdf`
4. 🔗 **[Artigo] Casos de Uso de IA e Analytics na Contabilidade Brasileira**
   * *Descrição:* Mapeamento de ferramentas de IA aplicadas ao planejamento tributário e KPIs de custos.

---

## 🔍 3. Engenharia de Prompts e "Cicatrizes" (Troubleshooting)

Esta seção documenta o processo iterativo para extrair as melhores análises do NotebookLM, destacando os testes, falhas e ajustes na construção dos prompts.

### 🔬 Testes e Evolução de Prompts

#### ❌ Tentativa 1 (Prompt Genérico / Pouco Efetivo)
* **Prompt:** *"Me explica o que é débito e crédito no Excel e no Power BI."*
* **Resultado Obtido:** A IA misturou os conceitos contábeis com operações de soma/subtração de planilhas e deu uma resposta genérica.
* **Problema:** O prompt foi ambíguo ao misturar a regra contábil com as ferramentas de software sem especificar o escopo.

#### ✅ Tentativa 2 (Prompt Refinado e Estruturado)
* **Prompt:** 
  > *"Com base estrita nos documentos das Quinzenas 1 e 3, responda: Como o entendimento do mecanismo de débito e crédito contábil afeta a estruturação do modelo de dados no Power Query? Apresente a resposta no formato de tabela comparativa destacando 'Conceito Contábil', 'Tratamento no ETL' e 'Erro Comum ao Ignorar'."*
* **Resultado Obtido:** O NotebookLM gerou uma tabela perfeita mostrando exatamente como contas credoras/devedoras devem ser sinalizadas (positivas/negativas) nas etapas de transformação do Power Query para evitar distorções no DRE.
* **Citação da Fonte:** Ref [1], pág 14 (PDF Contabilidade) e Ref [3], pág 5 (Power Query).

---

### 🩹 "Cicatrizes" e Aprendizados de Troubleshooting
1. **Desafio do PDF Escaneado:** Inicialmente, um dos PDFs de normas contábeis continha páginas escaneadas sem camada de texto (OCR). O NotebookLM ignorou o conteúdo. **Solução:** O arquivo foi reprocessado via OCR antes do upload.
2. **Escopo de IA:** Ao perguntar sobre impostos locais, o NotebookLM informou que a informação não constava nas fontes. **Aprendizado:** Confirmou-se a eficácia da IA ancorada (*grounded*) em não inventar fatos (*alucinação*), exigindo a inclusão de um documento específico sobre legislação tributária local no caderno.

---

## 📖 4. Miniguia de Estudo (Entrega Final)

### 📌 Resumos Estruturados por Quinzena

#### Quinzena 1: Fundamentos Contábeis e Legislação
* **Mecanismo de Débito e Crédito:** Débito representa a aplicação de recursos; Crédito representa a origem dos recursos. A natureza das contas (Ativo = Devedora, Passivo/PL = Credora) determina como os lançamentos impactam o patrimônio.
* **Regime de Caixa vs. Competência:** O regime de competência reconhece receitas e despesas no fato gerador, enquanto o de caixa considera apenas o fluxo financeiro efetivo.

#### Quinzena 2: Automação no Excel
* **Listas Dinâmicas (`DESLOC` + `CONT.VALORES`):** A combinação dessas funções permite criar intervalos de validação que expandem automaticamente conforme novas linhas de lançamentos são inseridas, evitando erros de digitação e refatoração manual.

#### Quinzena 3: ETL e Power BI
* **Dependência de Passos no Power Query:** Cada alteração na Linguagem M afeta em cascata os passos seguintes. Alterar o tipo de uma coluna no início pode quebrar mesclagens ou agregações futuras.

#### Quinzena 4: Dashboards e IA
* **Análise Preditiva e Simulações *What-If*:** Utilização de modelos de linguagem combinados com scripts de visualização para simular cenários tributários e gerar KPIs operacionais automaticamente.

---

### 📚 Glossário de Conceitos Chave

| Termo | Categoria | Definição Prática |
| :--- | :--- | :--- |
| **Fato Gerador** | Contabilidade | Evento que estabelece a obrigação tributária ou a necessidade de registro contábil pelo regime de competência. |
| **ETL** | Dados / BI | *Extract, Transform, Load* — Processo de extrair dados de fontes (ex: Excel/ERP), limpa-los e carregá-los no modelo do Power BI. |
| **Linguagem M** | Power BI | Linguagem de fórmulas estruturada utilizada no Power Query para transformação de dados. |
| **Intervalo Dinâmico** | Excel | Recurso que ajusta automaticamente a amplitude de um intervalo selecionado usando fórmulas como `DESLOC`. |

---

### 🤖 Conjunto de Prompts Reutilizáveis (Biblioteca de Prompts)

Coleção de prompts validados para utilizar em revisões futuras dentro do NotebookLM:

#### 1. Prompt para Síntese Comparativa
```text
Com base nos materiais carregados, compare [Conceito A] e [Conceito B]. Apresente uma tabela contendo: Definição, Aplicação Prática, Impacto Financeiro e 1 Exemplo Real.
