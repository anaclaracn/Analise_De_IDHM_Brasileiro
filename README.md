# Análise Do Índice de Desenvolvimento Humano Municipal Brasileiro

## Introdução

O desenvolvimento humano é um conceito multidimensional que reflete não apenas o crescimento econômico, mas também as oportunidades reais de uma população viver uma vida longa, saudável e com acesso à educação e renda dignas. No Brasil, as desigualdades regionais e sociais criam cenários contrastantes entre estados e municípios, o que torna essencial compreender **quais fatores mais influenciam a evolução do Índice de Desenvolvimento Humano Municipal (IDHM)** e suas três dimensões: **Educação**, **Renda** e **Longevidade**.

Diante desse contexto, este trabalho tem como objetivo **avaliar e explorar os principais agentes e fenômenos que impactam o desenvolvimento socioeconômico brasileiro**, utilizando dados do **Atlas do Desenvolvimento Humano no Brasil**.

A partir da coleta e integração de múltiplos índices, abrangendo aspectos **educacionais, econômicos, ambientais e sociais**, a análise visa identificar **padrões de correlação e interdependência** entre variáveis, bem como compreender **como fatores estruturais (como renda, escolaridade e desigualdade)** moldam a qualidade de vida da população brasileira.

Além da etapa descritiva e exploratória, o estudo busca responder à seguinte questão central:

> **Como poderíamos avaliar e prever/visualizar os agentes e fenômenos que mais causam impactos socioeconômicos no Brasil?**

A resposta a essa pergunta passa pela investigação de quais variáveis mais se correlacionam com os componentes do IDHM e de que forma essas relações podem ser visualizadas e interpretadas. Para isso, a análise combina **técnicas estatísticas e exploratórias de dados**, com visualizações gráficas que destacam **as 30 variáveis mais correlacionadas** com cada dimensão do índice.  


## 🧩 Escolha dos Dados  

Os dados utilizados neste projeto foram obtidos a partir do **[Atlas do Desenvolvimento Humano no Brasil](http://www.atlasbrasil.org.br/consulta/planilha)**.

Essa escolha se deve ao fato de o Atlas ser uma das fontes **mais completas e consolidadas** sobre indicadores **socioeconômicos, educacionais, demográficos e territoriais** do Brasil, reunindo informações padronizadas e comparáveis entre diferentes regiões, estados e municípios.  

### 🎯 Relação com o objetivo do projeto  
O desafio proposto busca responder à pergunta:  
> **“Como poderíamos avaliar e prever/visualizar os agentes e fenômenos que mais causam impactos socioeconômicos no Brasil?”**

Para isso, é essencial o uso de bases de dados **multidimensionais e integradas**, capazes de capturar as diferentes dimensões que influenciam o desenvolvimento humano. O Atlas Brasil cumpre exatamente esse papel ao disponibilizar variáveis relacionadas a:  
-  **Renda e desigualdade econômica**  
-  **Educação e escolaridade**  
-  **Longevidade e saúde pública**  
-  **Condições urbanas e rurais**  
-  **Emprego, formalização e vulnerabilidade social**  

### Representatividade e diversidade  
Outro motivo crucial para a escolha dessa base é a sua **abrangência nacional** e **granularidade**: o Atlas fornece dados **agregados e desagregados**, permitindo comparar **municípios, estados e regiões** e compreender como o desenvolvimento varia segundo o contexto territorial e social.  

Essa característica é especialmente importante ao tratar da **diversidade brasileira**, marcada por desigualdades regionais, históricas e estruturais. Dessa forma, o conjunto de dados do Atlas possibilita uma análise profunda sobre **como fatores locais e regionais influenciam os componentes do IDHM** — Renda, Educação e Longevidade.  


## 🧠 Metodologia de Aquisição dos Dados  

A etapa de aquisição dos dados foi realizada de forma **manual e criteriosa**, diretamente pelo site do **[Atlas do Desenvolvimento Humano no Brasil](http://www.atlasbrasil.org.br/consulta/planilha)**.  

Inicialmente, o projeto tinha como objetivo trabalhar com **dados municipais**, a fim de captar a diversidade local e as desigualdades intraestaduais. No entanto, após uma análise inicial, observou-se que:  
- Muitos **índices e indicadores** não estavam disponíveis para **todos os municípios**;  
- O volume de informações seria **muito elevado**, dificultando a limpeza, unificação e análise dos dados;  
- Havia **maior consistência e comparabilidade** nas informações quando analisadas em **nível estadual**.  

Dessa forma, optou-se por **agregar os dados por estado**, garantindo uma base mais **uniforme, equilibrada e completa** para as análises.  

### 🗂️ Processo de Coleta  
A coleta seguiu as seguintes etapas:  
1. Acesso ao portal do **Atlas Brasil**;  
2. Seleção dos conjuntos de dados disponíveis em formato **.xlsx** referentes a diferentes dimensões socioeconômicas;  
3. Download individual de cada base, respeitando o nível **estadual de agregação**;  
4. Organização dos arquivos em oito principais frentes de análise:  
   - **IDH e seus componentes (Renda, Educação, Longevidade)**  
   - **Educação e escolaridade**  
   - **Habitação, meio ambiente e políticas públicas**  
   - **População e demografia**  
   - **Renda e desigualdade**  
   - **Saúde e bem-estar**  
   - **Trabalho e emprego**  
   - **Vulnerabilidade social**  

Cada base foi posteriormente carregada, inspecionada e padronizada no **notebook de análise**, garantindo consistência entre nomes de colunas e variáveis, etapa essencial para a integração final em um **dataframe unificado**.  

### 💡 Decisão Metodológica  
A escolha por trabalhar com dados **em nível estadual** foi estratégica:  
- Permitiu **comparações diretas** entre regiões e estados;  
- Evitou lacunas de dados que poderiam comprometer a análise;  
- Manteve o foco no **entendimento de padrões amplos e estruturais** de desigualdade e desenvolvimento;  
- Conservou a representatividade da **diversidade socioeconômica brasileira**, sem perda de coerência estatística.  

Essa abordagem equilibra **abrangência e profundidade**, oferecendo uma visão consolidada dos principais fatores que influenciam o desenvolvimento humano no Brasil.


## 🧩 Principais Passos do Notebook  

O notebook desenvolvido seguiu uma estrutura lógica e sequencial para garantir a **organização, limpeza, integração e análise** dos dados coletados.  
Cada etapa teve o objetivo de preparar a base para uma análise exploratória consistente, que permitisse responder à pergunta central do projeto.  

---

### 1️⃣ Importação e Leitura dos Dados  
Foram importados oito conjuntos de dados obtidos do **Atlas Brasil**, cada um representando uma dimensão socioeconômica do país.  
Cada planilha foi carregada em um **DataFrame individual**, garantindo a separação por tema (educação, saúde, renda, etc.).

---

### 2️⃣ Tratamento e Padronização das Bases  
Nesta etapa, foram aplicados procedimentos para **limpar e uniformizar** os dados:  
- Remoção de **linhas de metadados** e informações desnecessárias;  
- Correção de **nomes de colunas** e padronização de formatos;  
- Identificação e tratamento de **valores nulos (NaN)**, pois os estados do **Distrito Federal e Roraima**, apresentavam lacunas e tiveram seus valores **estimados pela média da região** mais coerente socioeconomicamente;  
- Verificação final garantindo que **todas as bases estivessem completas e consistentes**.  

---

### 3️⃣ Unificação das Bases  
Com os DataFrames limpos, foi realizada a **integração progressiva** das tabelas usando a coluna `Territorialidades` (nome dos estados).  
Esse processo resultou em um **DataFrame unificado**, consolidando todas as dimensões socioeconômicas em uma única estrutura.  
Foram removidas colunas duplicadas (sufixos `_x` e `_y`), mantendo apenas as versões consolidadas de cada variável.

---

### 4️⃣ Análise das Relações Entre os Indicadores  
A análise exploratória teve como foco identificar **correlações entre os principais índices de desenvolvimento humano**:  
- **IDHM 2010 (geral)**  
- **IDHM Educação 2010**  
- **IDHM Renda 2010**  
- **IDHM Longevidade 2010**  

Para cada um, foram calculadas e visualizadas:  
- As **20 variáveis mais correlacionadas** (positivas ou negativas);  
- **Mapas de calor (heatmaps)** para visualizar relações diretas entre os índices;  
- **Gráficos de barras** com as variáveis de maior correlação absoluta (≥ 0.85), permitindo identificar os fatores com **maior impacto socioeconômico**.
- **Gráficos de linhas** para visualizar a distribuição por estado.


## 🔍 Principais Insights da Análise Exploratória  

A análise exploratória dos dados revelou **relações profundas entre as diferentes dimensões do desenvolvimento humano no Brasil**, mostrando como fatores estruturais — educação, renda e longevidade — se entrelaçam para moldar os níveis de qualidade de vida nos estados brasileiros.  

---

### 📊  IDHM Geral  
No índice agregado (IDHM total), observam-se variáveis combinadas das três dimensões:
- **Taxas de escolarização (18–24 anos com ensino médio completo)**;  
- **Renda per capita (por quintis)**;  
- **Grau de formalização dos ocupados**;  
- **PIB per capita e IDHM ajustado à desigualdade**.

O comportamento do IDHM total demonstra **a interdependência entre educação, renda e saúde**. As variáveis mais correlacionadas são as mesmas que estruturam o desenvolvimento humano: **educação básica de qualidade, distribuição equitativa da renda e inserção formal no mercado de trabalho**.  

Essa convergência mostra que o progresso em uma dimensão tende a impulsionar as outras:  
- Educação melhora a empregabilidade e formalização;  
- Renda possibilita acesso à saúde e melhores condições de vida;  
- Saúde garante longevidade produtiva e manutenção do ciclo de desenvolvimento.

Em contrapartida, déficits em uma dimensão criam **círculos de vulnerabilidade**, especialmente nas regiões mais pobres, onde a desigualdade agrava as dificuldades de acesso a educação e saúde.  
O **IDHM ajustado à desigualdade** reforça essa leitura, mostrando que a distribuição dos ganhos é tão importante quanto o crescimento em si.

O **IDHM total** consolida essas dimensões, refletindo de forma clara o padrão de desigualdade regional no Brasil. Observa-se um **bloco de estados do Norte e Nordeste** com índices entre 0,63 e 0,69, enquanto os **estados do Sul e Sudeste** se destacam com valores acima de 0,75.  
Essa diferença evidencia como políticas públicas voltadas à **educação e infraestrutura social** podem impactar positivamente o desenvolvimento humano em regiões menos favorecidas.

<img width="1116" height="790" alt="IDHM" src="https://github.com/user-attachments/assets/febc7f75-a898-4fb1-b43a-9373335af8bb" />
<img width="1389" height="690" alt="G_IDHM" src="https://github.com/user-attachments/assets/565f09f8-0415-425e-8784-61be746679be" />


---

### 🎓  IDHM Educação  

Entre as variáveis mais correlacionadas com o **IDHM Educação**, destacam-se:
- **% de jovens de 18 a 24 anos com ensino médio completo** (geral, urbano e rural);  
- **Taxa de frequência líquida ao ensino médio**;  
- **% de jovens de 18 a 20 anos com ensino fundamental completo**;  
- **Subíndice de escolaridade do próprio IDHM Educação**;  
- **Médias de renda per capita dos quintis mais baixos e intermediários**.
  
O IDHM Educação reflete de maneira direta **a permanência e conclusão escolar nas faixas etárias de transição entre juventude e vida adulta**. Essa etapa (18–24 anos) é decisiva porque concentra o término do ciclo básico e o ingresso no ensino superior ou mercado de trabalho.  

A presença de variáveis econômicas entre as mais correlacionadas evidencia o impacto das **condições socioeconômicas sobre o sucesso escolar**. Estados com **melhor renda domiciliar per capita** e **menores desigualdades regionais** apresentam maiores taxas de conclusão do ensino médio. Isso reforça a tese de que **a pobreza e a vulnerabilidade econômica ainda são barreiras significativas à continuidade dos estudos**, especialmente nas regiões Norte e Nordeste.  

Além disso, a **frequência líquida ao ensino médio** mostra que o desafio não é apenas o acesso, mas a **permanência e progressão escolar**, o que demanda políticas integradas de apoio estudantil, transporte, e inclusão digital.  

A Educação é o componente com **maior variação entre os estados**, destacando-se como um dos principais gargalos para o desenvolvimento humano. Estados como **Distrito Federal, São Paulo e Santa Catarina** lideram, enquanto **Alagoas e Pará** ainda enfrentam grandes desafios. Esse indicador é crucial, pois influencia diretamente renda e longevidade a longo prazo.

Em suma, o IDHM Educação revela que **o capital humano é profundamente condicionado pelo contexto socioeconômico**, e que o rompimento desse ciclo requer políticas públicas focadas na **equidade educacional e redução das desigualdades regionais**.

<img width="1180" height="790" alt="Educação" src="https://github.com/user-attachments/assets/41b30f9d-f07e-419e-a431-0c526abc77a7" />
<img width="1390" height="690" alt="G_Educacao" src="https://github.com/user-attachments/assets/027ac7fc-7a3e-42cf-b26d-d433daf1ef2d" />


---

### 💰  IDHM Renda  
No componente **Renda**, as variáveis mais associadas incluem:
- **Renda domiciliar per capita média e máxima dos quintis 3º, 4º e 5º**;  
- **Rendimento médio dos ocupados e rendimento do trabalho por décimo de renda**;  
- **PIB per capita e valor adicionado per capita**;  
- **Grau de formalização dos ocupados**;  
- **Proporção de trabalhadores com rendimento até meio salário mínimo** (em correlação negativa).

A dimensão renda do IDHM não é determinada apenas pela riqueza média de cada estado, mas **pela forma como essa riqueza é distribuída**. A presença dominante de variáveis de **quintis e décimos de renda** mostra que **a desigualdade é um fator estrutural**, regiões onde o crescimento se concentra apenas nos grupos mais ricos têm IDH mais baixos.  

O **grau de formalização do trabalho** aparece como uma ponte entre mercado e inclusão social. Locais com maior formalização não apenas apresentam rendas mais estáveis, mas também garantem **acesso a direitos trabalhistas e previdenciários**, que impactam positivamente indicadores como longevidade e segurança econômica.

Outro ponto importante é o **valor adicionado per capita**, que reflete a produtividade econômica e a diversificação de atividades. Estados com economias mais diversificadas e industrializadas (ex.: Sul e Sudeste) concentram os maiores valores, enquanto Norte e Nordeste ainda dependem fortemente de setores de baixo valor agregado.  

Observa-se uma forte disparidade entre as regiões: estados como **Maranhão, Piauí e Alagoas** apresentam os menores valores, enquanto **Distrito Federal, São Paulo e Rio de Janeiro** concentram as maiores rendas. Essa diferença reflete o desequilíbrio econômico estrutural do país, influenciado pela concentração de oportunidades e infraestrutura.

Portanto, o IDHM Renda expressa mais do que a renda em si: ele **traduz as disparidades regionais de oportunidade econômica**, reforçando que crescimento sustentável exige **inclusão produtiva e formalização**, e não apenas aumento da média salarial.

<img width="1151" height="790" alt="Renda" src="https://github.com/user-attachments/assets/d09fe8c5-22fc-4fac-9cbf-37b79b8f86f0" />
<img width="1389" height="690" alt="G_Renda" src="https://github.com/user-attachments/assets/cac21d0c-cca9-4a2f-9d5b-8c7c54721db2" />


---

### ❤️  IDHM Longevidade  
Na dimensão **Longevidade**, as variáveis mais correlacionadas incluem:
- **Esperança de vida ao nascer (urbana e rural)**;  
- **IDHM ajustado à desigualdade**;  
- **Diversas medidas de renda per capita e renda domiciliar (por quintis)**;  
- **Taxa de formalização e indicadores de trabalho**;  
- **Indicadores educacionais da faixa de 18–24 anos**.
 
A longevidade é uma medida-síntese dos **determinantes sociais da saúde**, e os resultados mostram isso com clareza. Estados com **maior renda média**, **menor desigualdade** e **maior escolarização** tendem a apresentar maior expectativa de vida.  

A forte correlação entre longevidade e indicadores de renda dos quintis mais pobres sugere que **a melhoria da renda das camadas inferiores é um dos fatores mais eficazes para ampliar a expectativa de vida**. Isso ocorre porque maior renda significa **melhor acesso à alimentação adequada, moradia, saneamento, prevenção e serviços de saúde**.  

A presença da **formalização do trabalho** reforça a importância de políticas de inserção laboral, trabalhadores formais têm maior estabilidade, acesso a planos de saúde e benefícios que impactam diretamente sua qualidade e tempo de vida.  

Além disso, a **educação aparece como variável transversal**, indicando que a instrução amplia a capacidade das pessoas de cuidar da própria saúde e fazer escolhas preventivas.  

A longevidade tende a ser mais homogênea entre os estados, embora ainda exista um gradiente claro entre Norte/Nordeste e Sul/Sudeste. Fatores como **acesso à saúde, saneamento e políticas públicas de prevenção** explicam a vantagem dos estados do Sul e do Sudeste.

Em resumo, o IDHM Longevidade revela que **saúde é reflexo de renda, educação e trabalho digno**, e que combater desigualdades sociais é também uma política de saúde pública.

<img width="1183" height="790" alt="Longevidade" src="https://github.com/user-attachments/assets/4ff4c974-75c3-4bf0-94b6-8ecc2800ee87" />
<img width="1389" height="690" alt="G_Longevidade" src="https://github.com/user-attachments/assets/79ac8014-35d3-476f-ac35-4cd7996990ae" />


---

### Interpretação Geral  
Os resultados reforçam a ideia de que o Brasil é **um mosaico de realidades socioeconômicas**, onde o desenvolvimento não é homogêneo, mas condicionado por **história, geografia e políticas regionais**.  
As análises mostraram que **nenhum indicador atua isoladamente**, renda, educação e saúde formam um **sistema interdependente**, em que avanços em uma área tendem a impulsionar as demais.  

Dessa forma, a visualização integrada das correlações permite compreender melhor **quais fatores possuem maior poder de impacto socioeconômico** e **quais regiões necessitam de políticas públicas mais direcionadas e inclusivas**.

---

## Como avaliar, prever e visualizar os agentes/fenômenos que mais causam impacto socioeconômico

Com base nas descobertas empíricas do estudo, é possível responder de forma prática à pergunta central do projeto:

> **Como poderíamos avaliar e prever/visualizar os agentes e fenômenos que mais causam impactos socioeconômicos no Brasil?**

1. **Avaliar**: utilizar análises de correlação e regressões múltiplas para quantificar o peso de cada variável (educação, renda, formalização, desigualdade) sobre o IDHM.  
2. **Prever**: aplicar modelos de *machine learning* para prever o IDHM a partir de múltiplos indicadores e medir a importância de cada variável.  
3. **Visualizar**: criar mapas interativos que mostrem espacialmente os padrões regionais de vulnerabilidade e desenvolvimento.  
4. **Interpretar e agir**: usar os resultados para embasar políticas públicas que priorizem **educação, distribuição de renda e formalização laboral**, as variáveis mais determinantes para o avanço do IDH no Brasil.


## Conclusão  
Em síntese, os dados apontam que **educação e renda são os principais motores do desenvolvimento humano** no Brasil, influenciando diretamente a longevidade e reduzindo vulnerabilidades sociais.  
Compreender essas relações de forma quantitativa é essencial para **avaliar e prever os fenômenos que mais afetam o desenvolvimento socioeconômico**, permitindo criar **estratégias regionais mais eficazes e sustentáveis** voltadas à promoção da equidade e do bem-estar coletivo.

