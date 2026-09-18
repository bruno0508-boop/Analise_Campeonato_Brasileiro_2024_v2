# Analise_Campeonato_Brasileiro_2024_v2

# 📊 Power BI - Dynamic HTML/CSS Sidebar Navigation Dashboard

[![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![DAX](https://img.shields.io/badge/DAX-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)](https://docs.microsoft.com/en-us/dax/)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/pt-BR/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org/pt-BR/docs/Web/CSS)

## 📌 Sobre o Projeto

Este projeto apresenta um relatório interativo desenvolvido no **Power BI**, utilizando uma abordagem avançada para **UI/UX Design de Relatórios**. Foi criada uma barra de navegação lateral (menu sidebar) customizada com **HTML e CSS via DAX**, oferecendo uma experiência de navegação fluida, moderna e reativa, semelhante à de uma aplicação web.

---

## 🚀 Funcionalidades Principais

- **Menu Lateral Dinâmico (Sidebar):** Renderizado via código HTML/CSS incorporado em medidas DAX no visual customizado de HTML Content.
- **Indicação da Página Ativa:** Lógica DAX que identifica automaticamente a página selecionada e destaca visualmente a aba correspondente na sidebar.
- **Microinterações e Animações:** Efeitos de *hover*, transições de borda e alteração de opacidade dos ícones utilizando CSS puro.
- **Otimização de Ícones:** Utilização de *Data URIs* / SVG vetorizado para manter o relatório leve e responsivo sem dependência de fontes externas.

---

## 🛠️ Tecnologias e Ferramentas Utilizadas

- **Power BI Desktop:** Modelagem de dados, criação de visuais e publicação do relatório.
- **DAX (Data Analysis Expressions):** Lógica condicional (`SELECTEDVALUE`, `COALESCE`) e montagem dinâmica de strings HTML/CSS.
- **HTML5 & CSS3:** Estruturação da barra lateral e estilização completa (flexbox, transições, estados `:hover` e `.active`).

---

## 💻 Estrutura da Medida DAX (Menu Lateral)

```dax
Menu_HTML = 
VAR PageAtiva = COALESCE(SELECTEDVALUE(dPaginas[ID_Pagina]), 1)
VAR Icone_Negocios = "data:image/png;base64,..."

RETURN
"
<style>
    .sidebar { background: #2D3547; width: 70px; display: flex; flex-direction: column; }
    .menu-item.active { border-color: #D06A84; background: #3d4961; }
</style>

<div class='sidebar'>
    <div class='menu-item " & IF(PageAtiva = 1, "active", "") & "' title='Visão Geral'>
        <img src='" & Icone_Negocios & "' />
    </div>
</div>
"
