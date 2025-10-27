# Analise_De_IDHM_Brasileiro

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

### 🌎 Representatividade e diversidade  
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


## 🔍 Principais Insights da Análise Exploratória  

A análise exploratória dos dados revelou **relações profundas entre as diferentes dimensões do desenvolvimento humano no Brasil**, mostrando como fatores estruturais — educação, renda e longevidade — se entrelaçam para moldar os níveis de qualidade de vida nos estados brasileiros.  

---

### 📊  IDHM Geral  
A correlação do **IDHM 2010** com os demais indicadores evidenciou que o desenvolvimento humano no Brasil é **fortemente determinado pela renda e pela educação**.  
Estados com **melhores índices de escolaridade e renda média** apresentam também **maior longevidade e menor vulnerabilidade social**.  
As regiões **Sul e Sudeste** se destacam com as maiores correlações positivas, enquanto **Norte e Nordeste** concentram as menores, reforçando o retrato histórico das **desigualdades regionais brasileiras**.

<img width="1116" height="790" alt="IDHM" src="https://github.com/user-attachments/assets/febc7f75-a898-4fb1-b43a-9373335af8bb" />


---

### 🎓  IDHM Educação  
O eixo educacional apresentou correlação extremamente forte com **indicadores de emprego formal, renda domiciliar e expectativa de vida**.  
Isso reforça a importância da **educação como base do desenvolvimento sustentável**, atuando como **fator multiplicador** que impacta diretamente outras dimensões sociais e econômicas.  
Os gráficos mostraram que **estados com maior acesso à educação e menor taxa de analfabetismo** possuem também **melhores indicadores de saúde e renda**, confirmando a interdependência entre essas dimensões.

<img width="1180" height="790" alt="Educação" src="https://github.com/user-attachments/assets/41b30f9d-f07e-419e-a431-0c526abc77a7" />


---

### 💰  IDHM Renda  
Os indicadores de renda mostraram-se altamente correlacionados com **emprego formal, produtividade e escolaridade**.  
Fatores ligados ao mercado de trabalho — como **nível de ocupação, rendimento médio e informalidade** — explicam grande parte da variação do IDHM.  
Estados com **economias mais diversificadas e industrializadas** (como São Paulo, Santa Catarina e Distrito Federal) apresentam padrões mais elevados, enquanto regiões mais dependentes de atividades primárias ainda enfrentam **maior vulnerabilidade econômica**.  

<img width="1151" height="790" alt="Renda" src="https://github.com/user-attachments/assets/d09fe8c5-22fc-4fac-9cbf-37b79b8f86f0" />


---

### ❤️  IDHM Longevidade  
A longevidade apresentou forte relação com **infraestrutura de saúde, saneamento básico, renda e escolaridade**.  
Os estados com **melhor acesso à saúde e menor desigualdade social** tendem a ter **expectativas de vida mais altas**, mostrando que a longevidade é reflexo direto do **bem-estar social e das condições de vida urbanas**.  
Essa correlação revela também como as **políticas públicas de saúde e saneamento** podem impactar significativamente o desenvolvimento humano de longo prazo.  

<img width="1183" height="790" alt="Longevidade" src="https://github.com/user-attachments/assets/4ff4c974-75c3-4bf0-94b6-8ecc2800ee87" />


---

### 🌎  Interpretação Geral  
Os resultados reforçam a ideia de que o Brasil é **um mosaico de realidades socioeconômicas**, onde o desenvolvimento não é homogêneo, mas condicionado por **história, geografia e políticas regionais**.  
As análises mostraram que **nenhum indicador atua isoladamente** — renda, educação e saúde formam um **sistema interdependente**, em que avanços em uma área tendem a impulsionar as demais.  

Dessa forma, a visualização integrada das correlações permite compreender melhor **quais fatores possuem maior poder de impacto socioeconômico** e **quais regiões necessitam de políticas públicas mais direcionadas e inclusivas**.

---

### Conclusão  
Em síntese, os dados apontam que **educação e renda são os principais motores do desenvolvimento humano** no Brasil, influenciando diretamente a longevidade e reduzindo vulnerabilidades sociais.  
Compreender essas relações de forma quantitativa é essencial para **avaliar e prever os fenômenos que mais afetam o desenvolvimento socioeconômico**, permitindo criar **estratégias regionais mais eficazes e sustentáveis** voltadas à promoção da equidade e do bem-estar coletivo.

