# ⚽ Brasileirão 2024 — Dashboard de Inteligência Esportiva & Gestão de Elenco

![Power BI](https://img.shields.io/badge/Power_BI-F2C94C?style=for-the-badge&logo=powerbi&logoColor=black)
![Power Query](https://img.shields.io/badge/Power_Query-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![Linguagem M](https://img.shields.io/badge/Linguagem_M-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
![Status](https://img.shields.io/badge/Status-Concluído-brightgreen?style=for-the-badge)

## 📌 Sobre o Projeto

Este projeto consiste em um dashboard executivo desenvolvido no **Power BI** para análise tática, financeira e de desempenho do **Campeonato Brasileiro Série A 2024**. 

O objetivo principal é transformar dados brutos de jogadores, clubes e estatísticas em uma solução *Data-Driven* de alta performance, permitindo que gestores do futebol avaliem a utilização do elenco, o retorno sobre investimento (ROI), o risco financeiro de lesões e o perfil etário das equipes.

> 🔄 **Evolução do Projeto:** Este repositório traz uma **releitura completa** de uma versão anterior criada há um ano. A nova solução apresenta um grande salto em engenharia de dados (ETL), consistência visual (UI/UX) em *Dark Theme* e profundidade nas métricas esportivas.

link do projeto anterior - https://github.com/bruno0508-boop/Analise-do-Campeonato-Brasileiro-Serie-A-2024

---

## 🖼️ Módulos & Páginas do Dashboard

O dashboard possui navegação lateral customizada dividida em 6 visões estratégicas:

1. 💼 **Visão Geral & Mercado:** Análise da folha salarial mensal/anual, valuation dos elencos e ranking de jogadores mais valiosos.
2. 🌳 **Árvore de Análise:** Decomposição hierárquica (Árvore de Decomposição) dos atletas por região, clube, nacionalidade e empresários.
3. 🔬 **Raio-X Elenco:** Mapeamento do perfil dos atletas e grupo econômico.
4. 📈 **Gestão de Risco & ROI Esportivo:** Relação Salário vs. Valor de Mercado, ROI dos elencos e impacto financeiro de lesões no Departamento Médico (DM).
5. ⚽ **Resumo da Temporada & Performance:** Aproveitamento dentro/fora de casa, arrecadação de bilheteria e rankings de artilheiros, assistências e desarmes.
6. 📋 **Gestão de Elenco:** Distribuição de minutagem por posição tática e perfil etário dos atletas.

---

## 🛠️ Tecnologias & Etapas de Engenharia de Dados

### 1. Tratamento e Transformação de Dados (Power Query / Linguagem M)
* **Padronização Tática:** Tradução em lote de siglas em inglês para os nomes por extenso em português via `List.Accumulate` (ex: `CB` → `Zagueiro`, `GK` → `Goleiro`, `DM` → `Volante`).
* **Categorização de Idades:** Construção de lógica condicional dinâmica para segmentar os atletas em faixas etárias:
  * **Até 22 anos:** `Jovem Promessa`
  * **23 a 26 anos:** `Em Afirmação`
  * **27 a 32 anos:** `Auge Profissional`
  * **Acima de 32 anos:** `Veterano`
* **Limpeza e Higienização:** Correção de valores nulos/ausentes e unificação de métricas de tempo de jogo e partidas.

### 2. Design e UI/UX
* **Tema Escuro (Dark Theme):** Paleta de cores personalizada baseada na identidade visual do campeonato.
* **Layout Modular:** Estruturação em cartões e blocos reutilizáveis.
* **Componentes Dinâmicos:** Filtros globais de região, clube, posição e faixa etária em todas as visões.

---

## 📊 Principais Insights do Projeto

* **Impacto das Lesões:** Acomodação do custo salarial parado no Departamento Médico (DM), demonstrando clubes que tiveram alto prejuízo individual por lesões.
* **Maturação vs. Minutagem:** A posição de Zagueiro e Volante concentrou a maior minutagem em atletas no *Auge Profissional* e *Veteranos*, enquanto posições de ponta tiveram maior participação de *Jovens Promessas*.
* **Eficiência Financeira:** Mapeamento da relação entre a folha salarial comprometida e a minutagem efetiva dentro de campo.

---

## 📂 Estrutura do Repositório

```text
├── 📁 dados/                  # Ficheiros e bases tratadas (.xlsx / .csv)
├── 📁 imagens/                # Screenshots do dashboard e wireframes
├── 📄 Script_PowerQuery.m     # Script M completo utilizado no ETL
└── 📄 README.md               # Documentação do projeto
