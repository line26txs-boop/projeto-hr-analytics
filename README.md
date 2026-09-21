# projeto-hr-analytics# Projeto HR Analytics - Visualização de Dados e Business Intelligence

**Aluno(a):** Aline da Purificação Santos
**Turma:** T3

## 1. Objetivo do Trabalho
Este projeto tem como objetivo realizar uma análise exploratória dos dados de Recursos Humanos (HR) da empresa. A intenção é compreender a distribuição de salários por departamento, cargo e região geográfica, fornecendo insights baseados em dados para apoiar decisões estratégicas da equipa de RH. O projeto engloba extração de dados com SQL, processamento e cálculos estatísticos em Python e visualização gráfica dos resultados.

## 2. Tabelas Utilizadas (Esquema HR)
A análise foi construída a partir do esquema Human Resources (HR) no banco de dados FreeSQL. As principais tabelas envolvidas foram:
* **EMPLOYEES:** Contém os dados primários dos funcionários (nome, salário, departamento).
* **DEPARTMENTS:** Informações sobre as áreas da empresa.
* **JOBS:** Detalhes sobre os cargos ocupados.
* **LOCATIONS, COUNTRIES, REGIONS:** Tabelas auxiliares utilizadas em conjunto para rastrear a distribuição geográfica completa (cidade, estado, país e região).

## 3. Resumo das Consultas SQL
Foram desenvolvidas duas consultas principais, ambas utilizando múltiplos comandos `LEFT JOIN` para garantir a integridade da extração mesmo em casos de dados incompletos.
* **Query 1 - Salários por Departamento e Cargo:** Analisa a relação direta entre o cargo do funcionário, o seu departamento e o seu salário atual. Filtro aplicado: `WHERE e.DEPARTMENT_ID IS NOT NULL` para excluir registos órfãos de departamento.
* **Query 2 - Distribuição Geográfica:** Mapeia cada funcionário até à sua região macro, cruzando dados de localizações, países e regiões. Filtro aplicado: `WHERE r.REGION_NAME IS NOT NULL`.

## 4. Análise Exploratória em Python (EDA)
Os dados exportados em CSV foram importados para um ambiente Jupyter Notebook utilizando a biblioteca Pandas. A análise incluiu:
* **Inspeção Estrutural:** Verificação do formato (106 linhas, 5 colunas), tipos de dados e confirmação da ausência de valores nulos ou duplicados, atestando a qualidade da extração.
* **Estatística Descritiva:** Cálculo de métricas fundamentais (média, mediana, mínimo, máximo e desvio padrão) para a coluna de salários.

## 5. Principais Resultados e Insights
A análise estatística revelou os seguintes indicadores salariais:
* **Média:** $6.456,75
* **Mediana:** $6.150,00
* **Mínimo:** $2.100,00
* **Máximo:** $24.000,00

**Insight Visual (Histograma e Boxplot):** A distribuição salarial possui uma "assimetria à direita". A grande maioria da força de trabalho concentra-se na faixa salarial mais baixa (entre $2.500 e $10.000). A presença de um valor atípico extremo (outlier) no valor de $24.000 distorce a média matemática, puxando-a para cima. A mediana ($6.150,00) provou ser a métrica mais representativa para a "realidade padrão" do funcionário nesta empresa.

## 6. Como Executar o Projeto
Siga os passos abaixo para reproduzir esta análise no seu ambiente:
1. Clone este repositório para a sua máquina local ou abra-o diretamente no GitHub Codespaces.
2. Certifique-se de que possui o Python instalado.
3. Abra o terminal na pasta raiz do projeto e instale as dependências necessárias executando o comando:
   `pip install pandas matplotlib`
4. Abra o ficheiro `notebooks/eda_hr.ipynb` num editor com suporte a Jupyter (como o VS Code) e execute as células sequencialmente.

## 7. Sugestões de Melhoria (Trabalhos Futuros)
* Implementar análises de correlação (ex: tempo de empresa vs. salário).
* Criar visualizações que cruzem o salário médio por departamento específico.

## 8. Vídeo de Apresentação
