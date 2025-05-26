# 📚 Dashboard Educacional: Desempenho de Alunos

Este projeto tem como objetivo analisar dados fictícios de alunos utilizando o **Power BI**, focando em indicadores de desempenho escolar, como notas, presença e taxa de aprovação.

---

## 🎯 Objetivos do Projeto

- Analisar o desempenho dos alunos em diferentes disciplinas e turmas.
- Visualizar a média geral de notas e a taxa de aprovação.
- Avaliar a correlação entre faltas e notas.
- Identificar a distribuição de faltas por aluno e por turma.
- Explorar tendências de desempenho ao longo dos períodos letivos.

---

## 🛠️ Ferramentas Utilizadas

- Power BI Desktop
- Excel (para geração da base de dados simulada)
- DAX (para criação de medidas e colunas calculadas)
- Gráficos interativos, segmentações e KPIs

---

## 📊 Visões Criadas

### Página 1 – Visão Geral
- KPI: Média Geral
- KPI: Taxa de Aprovação
- KPI: Total de Alunos
- Gráfico: Média por Disciplina
- Gráfico: Nota vs Faltas
- Tabela: Presenças e Faltas por Aluno
- Segmentações: Turma, Professor, Disciplina, Período

### Página 2 – Desempenho por Aluno
- Filtro de Aluno (Segmentação de dados)
- Tabela detalhada: Nome do Aluno, Disciplina, Nota, Faltas Ajustadas, Presenças
- Cartões: Média de Notas do Aluno, Total de Faltas do Aluno, % de Presença

### Página 3 – Comparativo entre Turmas
- Gráfico de Colunas: Média de Nota por Turma
- Gráfico de Pizza: Faltas Totais por Turma
- Cartões com KPIs por turma

---

## 🔍 Principais Métricas Criadas (DAX)

## 🔍 Principais Métricas Criadas (DAX)

```DAX
Média Geral = AVERAGE('Base'[Nota])
Taxa de Aprovação = 
VAR TotalLinhas = COUNTROWS('Base')
VAR Aprovados = COUNTROWS(FILTER('Base', 'Base'[Nota] >= 6))
RETURN DIVIDE(Aprovados, TotalLinhas)

Total de Alunos = DISTINCTCOUNT('Base'[Aluno])
Faltas Ajustadas = 
VAR TotalAulas = 40
VAR FaltasOriginais = 'Base'[Faltas]
RETURN
IF(FaltasOriginais > 10, 
   ROUND(RAND() * 8, 0), 
   FaltasOriginais
)
Presenças Ajustadas = 
40 - 'Base'[Faltas Ajustadas]
```

---
📂 Estrutura da Base de Dados
A base simulada contém os seguintes campos:

Aluno, Turma, Disciplina, Professor
Nota, Presenças, Faltas, Período
## 🖼️ Demonstração

### Página 1  
![Dashboard Educacional Página 1](./Screenshot_1.png)

### Página 2  
![Dashboard Educacional Página 2](./Screenshot_2.png)

### Página 3  
![Dashboard Educacional Página 3](./Screenshot_3.png)

---


🧠 O que Aprendi
Análise de dados educacionais com foco em desempenho
Criação de KPIs e medidas DAX relevantes
Uso de gráficos interativos e segmentações
Construção de painéis de visualização de dados educacionais
🚀 Próximos Passos
Adicionar comparação de desempenho entre períodos
Implementar análise de desempenho por gênero
Integrar com fontes de dados externas para análises em tempo real
📎 Arquivos incluídos
Dashboard_Educacional_PowerBI.pbix – Arquivo Power BI
Dashboard_Educacional_PowerBI.xlsx – Base de dados simulada
Imagens (pagina1.png, pagina2.png, pagina3.png) – Capturas das páginas
