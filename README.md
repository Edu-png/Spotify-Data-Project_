# Spotify Streaming Insights: Análise e Previsão de Tendências Musicais

![CAPAS - PROJETOS (4)](https://github.com/user-attachments/assets/d0973170-ddf4-4217-9c44-ca945e1f4a53)

## Sumário 🎯

1. [Resumo 🏃‍♀️](#resumo-)
2. [Introdução ☀](#introdução-)
   - [Objetivo 🎯](#objetivo-)
3. [Pipeline do Projeto 🛠](#pipeline-do-projeto-)
   - [Coleta de Dados](#1-coleta-de-dados)
   - [Pré-processamento de Dados](#2-pré-processamento-de-dados)
   - [Análise Exploratória de Dados (EDA)](#3-análise-exploratória-de-dados-eda)
   - [Modelagem](#4-modelagem)
   - [Avaliação e Interpretação dos Resultados](#5-avaliação-e-interpretação-dos-resultados)
   - [Implantação e Monitoramento](#6-implantação-e-monitoramento)
   - [Documentação e Divulgação](#7-documentação-e-divulgação)
   - [Modelo em Power BI](#8-modelo-em-power-bi)
4. [Métodos](#métodos)
   - [Exploração Inicial dos Dados](#1-exploração-inicial-dos-dados)
   - [Análises Baseadas em Popularidade](#2-análises-baseadas-em-popularidade)
   - [Organização Temporal](#3-organização-temporal)
   - [Transformações de Dados](#4-transformações-de-dados)
   - [Análise de Correlações](#5-análise-de-correlações)
   - [Tendências de Duração ao Longo do Tempo](#6-tendências-de-duração-ao-longo-do-tempo)
   - [Análise por Gêneros](#7-análise-por-gêneros)
   - [Ferramentas Utilizadas](#8-ferramentas-utilizadas)
5. [Resultados e Conclusões 📈](#resultados-e-conclusões-)
   - [Mapa de Correlação](#1-mapa-de-correlação)
   - [Correlações entre Variáveis](#2-correlações-entre-variáveis)
     - [Energia vs Intensidade Sonora](#a-energia-vs-intensidade-sonora-correlação-positiva)
     - [Energia vs Acústica](#b-energia-vs-acústica-correlação-negativa)
     - [Duração vs Liveness](#c-duração-vs-liveness-sem-correlação)
   - [Distribuição de Músicas por Ano](#3-distribuição-de-músicas-por-ano)
   - [Duração das Músicas ao Longo do Tempo](#4-duração-das-músicas-ao-longo-do-tempo)
     - [Gráfico de Barras](#a-gráfico-de-barras)
     - [Gráfico de Linha](#b-gráfico-de-linha)
   - [Análise por Gêneros](#5-análise-por-gêneros)
     - [Duração por Gênero](#a-duração-por-gênero)
     - [Popularidade por Gênero](#b-popularidade-por-gênero)
6. [Considerações Finais 🚀](#considerações-finais-)
7. [Bibliotecas Utilizadas e Suas Respectivas Funções 🐍](#bibliotecas-utilizadas-e-suas-respectivas-funções-)
8. [Referências 📄](#referências-)
9. [Documentação 📚](#documentação-)
10. [Agradecimentos 👏](#agradecimentos-)
11. [Contato 📪](#contato-)

---

## Resumo 🏃‍♀️
Neste projeto, analisei dados do Spotify com o objetivo de explorar padrões e tendências relacionados às músicas. Utilizando dois conjuntos de dados principais, comecei com a leitura e visualização preliminar das informações disponíveis. Identifiquei que o dataset contém colunas com valores nulos, mas em quantidades mínimas que não afetam significativamente as análises.

Inicialmente, verifiquei as músicas menos populares, organizando-as em ordem crescente de popularidade, e também identifiquei as músicas mais populares, focando em canções que possuem uma pontuação acima de 90 na métrica de popularidade. Em seguida, organizei as músicas por data de lançamento para observar padrões temporais e realizei conversões de unidades, como transformar a duração das músicas de milissegundos para segundos.

Explorei as correlações entre variáveis, criando um mapa de calor que destacou fortes relações, como a correlação positiva entre energia e intensidade sonora (loudness) e a ausência de relação entre energia e acústica. Para visualizações adicionais, usei um conjunto amostral menor para criar gráficos de dispersão, destacando correlações positivas e negativas entre variáveis como energia versus intensidade sonora e energia versus acústica, respectivamente.

Além disso, criei um gráfico de distribuição que mostra a quantidade de músicas lançadas por ano. Identifiquei que a maior parte dos lançamentos ocorreu após os anos 2000, com um pico significativo em 2019. Complementando essa análise, desenvolvi gráficos de barras e linhas que relacionam a duração média das músicas ao longo dos anos, revelando tendências interessantes.

Por fim, realizei uma análise específica por gêneros musicais utilizando um segundo dataset. Explorei a duração média das músicas por gênero e ordenei os gêneros mais populares, destacando os 10 principais em termos de popularidade. Essa abordagem trouxe insights adicionais sobre preferências musicais e características dos diferentes estilos.

O projeto utilizou diversas ferramentas e técnicas de visualização, como mapas de calor, gráficos de dispersão, gráficos de barras e linhas, para apresentar as descobertas de forma clara e objetiva, contribuindo para uma compreensão aprofundada do universo musical do Spotify.

## Introdução ☀
Este projeto teve como objetivo analisar dados do Spotify para identificar padrões em popularidade, duração e características musicais ao longo do tempo. Utilizei dois conjuntos de dados principais, explorando variáveis como energia, acústica e intensidade sonora, além de realizar análises específicas por gênero musical. Com o apoio de técnicas de visualização e estatísticas, destaquei insights relevantes sobre as tendências da indústria musical e as preferências dos ouvintes.

### Objetivo 
O objetivo deste projeto foi explorar e analisar dados do Spotify para identificar padrões e tendências em popularidade, duração e características das músicas, além de entender as relações entre variáveis como energia, intensidade sonora e acústica. Busquei também investigar como essas características variam ao longo do tempo e entre diferentes gêneros musicais, gerando insights que contribuem para a compreensão do comportamento da indústria musical e das preferências dos ouvintes.

## Pipeline do Projeto

### 1. **Coleta de Dados:**
   - Utilização da API do Spotify para obter informações detalhadas sobre faixas, artistas, álbuns e hábitos de escuta dos usuários.
   - Extração de dados públicos de outras fontes para complementar a análise.

### 2. **Pré-processamento de Dados:**
   - **Limpeza de Dados:** Remoção de valores ausentes, duplicatas e outliers. 
   - **Transformação de Dados:** Conversão de variáveis categóricas em numéricas, normalização de dados, e criação de novas features a partir das existentes, como a popularidade normalizada de músicas ao longo do tempo.

### 3. **Análise Exploratória de Dados (EDA):**
   - Visualizações para identificar padrões e tendências nos dados, como a popularidade de gêneros musicais, variação na popularidade de artistas, e comportamento de escuta dos usuários ao longo do tempo.
   - Análise estatística para entender a distribuição dos dados e relações entre diferentes variáveis.

### 4. **Modelagem:**
   - **Seleção de Modelos:** Escolha de algoritmos de machine learning adequados, como regressão linear, árvores de decisão e redes neurais.
   - **Treinamento de Modelos:** Divisão dos dados em conjuntos de treinamento e teste. Treinamento dos modelos utilizando o conjunto de treinamento.
   - **Validação de Modelos:** Avaliação do desempenho dos modelos utilizando métricas como precisão, recall, F1-score, e AUC-ROC.

### 5. **Avaliação e Interpretação dos Resultados:**
   - Análise dos resultados dos modelos para identificar os fatores que mais influenciam a popularidade das músicas.
   - Interpretação dos insights obtidos e identificação de padrões de comportamento dos usuários.

### 6. **Implantação e Monitoramento:**
   - Desenvolvimento de dashboards e relatórios para visualização contínua dos dados e insights.
   - Monitoramento do desempenho dos modelos e atualização com novos dados conforme necessário.

### 7. **Documentação e Divulgação:**
   - Documentação detalhada de todo o processo, incluindo código, análise de dados, resultados e conclusões.
   - Compartilhamento dos resultados e insights através de publicações, apresentações, ou repositórios de código, como GitHub.

### 8. **Modelo em Power BI:**
   - Desenvolvimento de um modelo em Power BI para visualização interativa dos dados e insights. O modelo permite aos usuários explorar tendências e padrões de maneira dinâmica, facilitando a análise e tomada de decisões.
   - O BI ainda não foi dispobilizado online mas conta com algumas prévias aqui nesse site!

## Métodos

Este projeto foi conduzido em várias etapas para garantir uma análise completa e organizada dos dados do Spotify. Abaixo, apresento as etapas detalhadas dos métodos utilizados:

---

### 1. Exploração Inicial dos Dados
- **Carregamento dos Dados:** 
  - Foram utilizados dois datasets: `tracks.csv` (contendo informações gerais das músicas) e `SpotifyFeatures.csv` (focado em gêneros musicais).
  - Os arquivos foram lidos utilizando a biblioteca `Pandas`.

- **Verificação de Dados Nulos:**
  - Utilizei o método `pd.isnull()` para identificar valores ausentes, garantindo que não houvesse impacto significativo nas análises.

- **Resumo Estatístico e Estrutura dos Dados:**
  - Com o método `info()` visualizei a estrutura das colunas.
  - Resumo estatístico foi obtido com `describe().transpose()` para compreender distribuições e valores médios.

---

### 2. Análises Baseadas em Popularidade
- **Músicas Menos e Mais Populares:**
  - Ordenei as músicas pela coluna `popularity` para identificar as 10 menos populares.
  - Filtrei músicas com `popularity > 90` para destacar as mais populares.

---

### 3. Organização Temporal
- **Datas de Lançamento:**
  - A coluna `release_date` foi convertida para o formato datetime, permitindo análises temporais detalhadas.
  - Organizei as músicas por data de lançamento para observar padrões históricos.

- **Distribuição por Ano:**
  - Criei um gráfico de distribuição com `sns.displot()` para visualizar o número de músicas lançadas por ano.

---

### 4. Transformações de Dados
- **Conversão de Unidades:**
  - Convertei a coluna `duration_ms` (milissegundos) para `duration` (segundos) utilizando uma função `lambda`.

- **Ajustes no Dataset:**
  - Removi colunas irrelevantes para análises específicas, como `key`, `mode` e `explicit`.

---

### 5. Análise de Correlações
- **Mapa de Calor:**
  - Utilizei `sns.heatmap()` para criar um mapa de calor, destacando correlações positivas (por exemplo, energia e intensidade sonora) e ausências de correlação (energia e acústica).

- **Gráficos de Dispersão:**
  - Criei gráficos de dispersão para explorar relações entre:
    - **Energia vs. Intensidade Sonora (correlação positiva).**
    - **Energia vs. Acústica (correlação negativa).**
    - **Duração vs. Liveness (sem correlação).**

---

### 6. Tendências de Duração ao Longo do Tempo
- **Gráfico de Barras:**
  - Relacionei a duração total das músicas ao ano de lançamento utilizando `sns.barplot()`.

- **Gráfico de Linha:**
  - Usei `sns.lineplot()` para observar tendências anuais de duração das músicas.

---

### 7. Análise por Gêneros
- **Duração por Gênero:**
  - Com o dataset `SpotifyFeatures.csv`, criei um gráfico de barras que relaciona gêneros musicais com a duração média das músicas.

- **Popularidade por Gênero:**
  - Ordenei os gêneros mais populares, destacando os 10 principais com um gráfico de barras.

---

### 8. Ferramentas Utilizadas
- **Bibliotecas Python:**
  - `Pandas` para manipulação de dados.
  - `Matplotlib` e `Seaborn` para visualizações.
  - `NumPy` para operações numéricas.

- **Plataformas de Desenvolvimento:**
  - Google Colab para execução e testes do código.
  - GitHub para versionamento e documentação do projeto.

---

## Resultados e Conclusões

### 1. Mapa de Correlação
O mapa de calor abaixo demonstra as correlações entre diferentes variáveis do conjunto de dados. Destaques:
- Forte correlação positiva entre **energia** e **intensidade sonora (loudness)**, indicando que músicas mais enérgicas tendem a ser mais altas.
- Ausência de correlação entre **energia** e **acústica**, sugerindo que músicas acústicas não necessariamente possuem menor energia.

![1](https://github.com/user-attachments/assets/01fd3ac3-890d-4bb0-8ded-bc9ea55a3ac6)

---

### 2. Correlações entre Variáveis
#### a) Energia vs Intensidade Sonora (Correlação Positiva)
Existe uma relação linear positiva entre **energia** e **intensidade sonora (loudness)**. Isso sugere que músicas mais altas são frequentemente percebidas como mais energéticas.

![2](https://github.com/user-attachments/assets/52388c9b-0c63-47e8-b826-22210b297f2e)

#### b) Energia vs Acústica (Correlação Negativa)
Foi identificada uma correlação negativa entre **energia** e **acústica**, indicando que músicas mais acústicas tendem a ser menos enérgicas.

![3](https://github.com/user-attachments/assets/263cdb43-e865-45a2-9653-7a2e8dcff95e)

#### c) Duração vs Liveness (Sem Correlação)
Não há evidências de uma relação significativa entre **duração** e **liveness**, reforçando que a duração de uma música não está ligada ao ambiente em que é gravada.

![4](https://github.com/user-attachments/assets/fc4c6e09-2cf3-41a1-9e65-ae115f0a9588)

---

### 3. Distribuição de Músicas por Ano
O gráfico de distribuição mostra o número de músicas lançadas por ano. Observações principais:
- O número de lançamentos aumenta significativamente após os anos 2000, com um pico em 2019.
- O crescimento pode estar relacionado ao advento de plataformas digitais.

![5](https://github.com/user-attachments/assets/7b30fc57-3ce1-4d38-b39f-22ea861e9c34)

---

### 4. Duração das Músicas ao Longo do Tempo
#### a) Gráfico de Barras
O gráfico de barras destaca a variação na duração média das músicas ao longo das décadas. Nota-se um padrão consistente, mas com pequenas flutuações.

![6](https://github.com/user-attachments/assets/63967fc3-e8a7-4075-92c1-3bf649fe8729)

#### b) Gráfico de Linha
O gráfico de linha reforça as tendências apresentadas anteriormente, detalhando os picos e quedas na duração média.

![7](https://github.com/user-attachments/assets/a9673aa7-9b95-4caf-a8cd-0c77b9d890d1)

---

### 5. Análise por Gêneros
#### a) Duração por Gênero
O gráfico a seguir mostra a duração média das músicas por gênero. Músicas de **opera** e **classical** apresentam maior duração, enquanto gêneros como **comedy** e **a capella** possuem durações menores.

![8](https://github.com/user-attachments/assets/8dfd15d1-1c90-4065-be3d-2b56e236a40e)

#### b) Popularidade por Gênero
Os gêneros mais populares incluem **Dance**, **Pop**, **Rap**, **Hip-Hop**, e **Reggaeton**, refletindo tendências globais da indústria musical.

![9](https://github.com/user-attachments/assets/1194e27a-8f9f-49f5-85cd-d707c0ed8d2a)

---

### Conclusões

1. **Correlações entre variáveis musicais:**
   - **Energia e Intensidade Sonora (Loudness):** Foi identificada uma forte correlação positiva, o que reforça a ideia de que músicas mais enérgicas tendem a ser percebidas como mais altas em volume. Isso pode ser atribuído ao fato de que músicas enérgicas são projetadas para provocar emoções intensas nos ouvintes, especialmente em gêneros como Dance e Pop.
   - **Energia e Acústica:** A correlação negativa sugere que músicas acústicas, como baladas ou estilos clássicos, possuem menos elementos de energia, refletindo um ritmo mais calmo e introspectivo.
   - **Duração e Liveness:** A ausência de correlação indica que a duração de uma música não está associada ao fato de ter sido gravada em um ambiente ao vivo. Isso pode ser explicado pela variedade de formatos de músicas ao vivo, que incluem desde performances curtas até extensos concertos.

2. **Tendências temporais no número de músicas:**
   - A análise revelou um aumento exponencial no número de músicas lançadas após os anos 2000, com um pico em 2019. Isso coincide com a popularização de serviços de streaming, como Spotify e Apple Music, que facilitaram a produção e a distribuição de músicas por artistas independentes e grandes gravadoras.
   - O aumento do acesso à tecnologia, como softwares de gravação e produção, também contribuiu para esse crescimento. Antes disso, os altos custos de produção e barreiras de entrada limitavam o número de lançamentos anuais.

3. **Duração das músicas ao longo do tempo:**
   - A duração média das músicas mostrou uma certa consistência, com pequenas flutuações ao longo das décadas. A partir dos anos 1980, nota-se uma leve redução na duração média, possivelmente devido à adaptação às preferências dos ouvintes e ao consumo de músicas em formatos mais curtos, como rádios e, mais recentemente, playlists digitais.
   - Apesar das tendências de redução, gêneros específicos, como música clássica e ópera, mantêm durações significativamente mais longas, preservando suas características tradicionais.

4. **Análise por gêneros:**
   - **Duração:** Gêneros como Ópera e Música Clássica possuem as músicas mais longas, refletindo a natureza narrativa e complexa dessas composições. Por outro lado, gêneros modernos como Pop, Hip-Hop e Dance têm uma duração mais curta, alinhada às demandas da audiência contemporânea, que busca músicas rápidas e cativantes.
   - **Popularidade:** Os gêneros mais populares, incluindo Dance, Pop, Rap, Hip-Hop e Reggaeton, indicam uma preferência global por estilos enérgicos e ritmados. Isso pode ser atribuído ao consumo em ambientes sociais, como festas, academias e eventos, onde esses gêneros desempenham um papel predominante.
   - A diversificação de gêneros no Spotify também reflete o impacto da globalização cultural, com estilos regionais, como Reggaeton, ganhando relevância em mercados internacionais.

5. **Impacto das características musicais na popularidade:**
   - Músicas populares tendem a apresentar uma combinação de energia, ritmo e intensidade sonora, enquanto atributos como acústica e instrumentalidade desempenham papéis menores. Isso demonstra uma preferência por músicas que são imediatamente envolventes e adequadas para ambientes dinâmicos, como festas ou academias.
   - A popularidade dos gêneros sugere que as tendências de consumo são influenciadas tanto pela cultura global quanto pelo marketing da indústria musical.

6. **Evolução da indústria musical:**
   - O crescimento na produção musical está intimamente ligado ao avanço tecnológico e à democratização do acesso a plataformas digitais. Esse cenário transformou o mercado, permitindo que artistas independentes tivessem alcance global.
   - O declínio na duração média das músicas nos últimos anos pode refletir as mudanças no comportamento do consumidor, como a preferência por playlists personalizadas e a menor atenção para faixas longas em um mundo de consumo rápido.

## Considerações finais 🚀
Essas análises demonstram como as características musicais, as preferências do público e a evolução tecnológica moldaram o panorama da música nos últimos 100 anos. Além disso, o estudo destaca a relevância do Spotify como ferramenta para compreender tendências culturais e comportamentais, fornecendo insights valiosos para artistas, produtores e profissionais da indústria musical.

### Bibliotecas utilizadas e suas respectivas funções 🐍
- **Pandas:** Manipulação de dados
- **NumPy:** Operações numéricas
- **Matplotlib & Seaborn:** Visualização de dados
- **Scikit-learn:** Ferramentas de machine learning
- **Spotipy:** Interface para a API do Spotify

## Referências 📄
- Documentação da API do Spotify: [Spotify API Documentation](https://developer.spotify.com/documentation/web-api/)
- Pandas Documentation: https://pandas.pydata.org/pandas-docs/stable/
- Scikit-learn Documentation: https://scikit-learn.org/stable/

## Documentação 📚
- **[Notebook da Limpeza dos Dados](link_do_notebook_limpeza)**
- **[Notebook da Análise Exploratória dos Dados](link_do_notebook_eda)**
- **[Notebook das Previsões com Machine Learning](link_do_notebook_ml)**

## Agradecimentos 👏
Agradecimentos especiais ao Spotify por fornecer acesso à sua API e aos desenvolvedores de bibliotecas open-source que tornaram este projeto possível e também ao site Kagle por disponibiliza-los! 

<div align="center">
  <img src="https://github.com/user-attachments/assets/54afb33c-97be-40b6-8c96-0f12852e946f" alt="thank-you" width="500">
</div>


## Contato 📪
- **LinkedIn:** [Eduardo Coqueiro](https://www.linkedin.com/in/eduardocoqueiro/)
- **Site:** [Eduardo Coqueiro](https://dataguy.my.canva.site/eduardo-coqueiro)
- **Kaggle:** [Eduardo Coqueiro](https://www.kaggle.com/eduardocoqueiro)
