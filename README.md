# Métodos extração de outliers
Neste repositório, realizo a comparação de diferentes métodos para a detecção de outliers, incluindo IQR, Z-Core, Isolation Forest e KNN. Meu objetivo é determinar qual desses métodos é mais adequado para o tipo de distribuição de dados em questão.

A detecção de outliers é uma etapa crucial na análise de dados, pois esses valores atípicos podem distorcer significativamente as análises estatísticas e os resultados dos modelos preditivos. Portanto, comparar e selecionar o método mais eficaz para identificar e tratar esses outliers é essencial para garantir a precisão e a confiabilidade das conclusões derivadas dos dados.

Cada método de detecção de outliers possui suas próprias vantagens e limitações, e a escolha do método mais apropriado depende da natureza dos dados e das características da distribuição subjacente. Ao realizar essa comparação, busco não apenas identificar o método mais preciso, mas também entender melhor as nuances dos dados e como diferentes métodos de detecção de outliers podem ser aplicados de forma eficaz em diferentes contextos analíticos.

## Data
Os dados contêm o tempo de atendimento (em dias) dos tickets da área de suporte de uma empresa, divididos em L1 (layer 1) e L2 (layer 2). O Tempo Total de Suporte é a soma dos tempos de L1 e L2, desde o ano de 2021 até 2024.

## O que são Outliers e por que detectá-los?
Um outlier é uma observação que se diferencia tanto das demais observações que levanta suspeitas de que aquela observação foi gerada por um mecanismo distinto” (Hawkins, 1980)

Detectar outliers é uma etapa crucial na análise de dados, pois ajuda a garantir a integridade, precisão e confiabilidade das conclusões derivadas dos dados. A presença de outliers pode distorcer as análises estatísticas e os resultados dos modelos preditivos, influenciando negativamente as interpretações feitas a partir dos dados. Portanto, identificar e tratar esses valores atípicos de forma adequada é fundamental para assegurar que as conclusões obtidas sejam válidas e representativas do verdadeiro comportamento dos dados.

## Nossos dados:
No Fig 1, por meio do histograma visualizamos a distribuição do nossos dados para L1, L2 e Suporte.
L1: Tempo de atendimento tem um range de 0 até 482 dias
L2: Tempo de atendimento tem um range de 0 até 349 dias
Suporte: Tempo de atendimento tem um range de 0 até 510 dias
<p align="center">
  <img src="https://github.com/katherinGriffi/M-todos_extra-o_outliers/blob/main/Histograma-original.png" width=80% height=80%>  
</p>

Na Fig2, por medio do grádico de outliers podemos detetar a presença de outliers (os pontos em preto)
<p align="center">
<img src="https://github.com/katherinGriffi/M-todos_extra-o_outliers/blob/main/boxplot.png" width=80% height=80%>
</p

Na Figura 3, realizei os cálculos das estatísticas e tanto em L1, L2 e Suporte podemos observar que a média é maior que a mediana, o que indica que a distribuição está inclinada para a direita (positivamente assimétrica). A maioria dos dados encontra-se à esquerda da média, isso também é possível observar na Figura 1. Este tipo de distribuição pode ser afetado por valores extremos.

No nível L2, o tempo médio de atendimento é ainda maior, em torno de 50.2 dias, com um desvio padrão de 59.9 dias. Isso indica uma variabilidade ainda maior nos tempos de atendimento em comparação com o nível L1, c

É evidente que os tempos de atendimento são significativamente mais longos no nível L2 em comparação com o nível L1. Isso sugere que as solicitações de suporte nos níveis L2 são mais complexas ou exigem mais tempo para serem resolvidas do que as do nível L1.

<p align="center">
<img src="https://github.com/katherinGriffi/M-todos_extra-o_outliers/blob/main/estatisticas-geral.JPG" width=80% height=80%>
</p>

# 1er Método - Itervalo Interquartil

Através desse método, outliers são definidos matematicamente como as observações que estão abaixo (Q1 − 1,5 x IQR) do "bigode inferior" do boxplot ou acima (Q3 + 1,5 x IQR) do "bigode superior" do boxplot.
<p align="center">
  <img src="https://github.com/katherinGriffi/M-todos_extra-o_outliers/blob/main/IQR.JPG" width=40% height=40%>  
</p>
Após o cálculo dos limites superior e inferior, procedemos com a detecção dos outliers, como pode ser observado na Figura 5.

<p align="center">
  <img src="https://github.com/katherinGriffi/M-todos_extra-o_outliers/blob/main/DetectionIQR.png" width=90% height=80%>  
</p>
Uma vez detectados os outliers, procedi com a remoção dos mesmos. Portanto, é possível observar nosso histograma e as estatísticas após a aplicação do 1º método nas Figuras 6 e 7.

<p align="center">
  <img src="https://github.com/katherinGriffi/M-todos_extra-o_outliers/blob/main/histo_1ermetodos.png" width=100% height=80%>  
   <img src="https://github.com/katherinGriffi/M-todos_extra-o_outliers/blob/main/estadisticas_1ermetodo.JPG" width=80% height=80%>  
</p>

##### Ao remover os outliers, observamos uma redução na variabilidade dos tempos de atendimento em todos os níveis de suporte (L1, L2 e Suporte total). Isso é evidenciado pela diminuição dos desvios padrão em relação aos valores originais, o que sugere uma distribuição dos dados mais concentrada em torno das medidas de tendência central.

##### Ao aplicar o método de Intervalo Interquartil para remover outliers, conseguimos melhorar a qualidade e a confiabilidade das análises dos tempos de atendimento nos diferentes níveis de suporte. Isso nos permite obter insights mais robustos e tomar decisões mais informadas para otimizar os processos de suporte e melhorar a experiência do cliente.

##### Como o método se concentra no quartil não é influenciado pela forma exacta da distribuição.

# 2do Método - Z_Core
O método Z-Score (ou escore Z) é uma medida estatística que indica quantos desvios padrão um ponto de dados está da média 
de um conjunto de dados.

##### Z = (X – μ) / σ
– μ é a média do conjunto de dados

– σ é o desvio padrão do conjunto de dados
<p align="center">
  <img src="https://github.com/katherinGriffi/M-todos_extra-o_outliers/blob/main/zcore.JPG" width=40% height=40%>  
</p>

Após calcular a média e o desvio padrão, calculei os limites superior e inferior e procedi à extração dos outliers. A distribuição de dados após a remoção dos outliers pelo método Z-Core pode ser observada na Figura 8.

<p align="center">
  <img src="https://github.com/katherinGriffi/M-todos_extra-o_outliers/blob/main/histo_2dometodos.png" width=100% height=80%>  
 </p>

Após aplicar o método Z-Core para remover outliers dos dados, foram identificados poucos outliers em comparação com o primer método, ainda observamos uma alta variabilidade significativa nos tempos de atendimento em todos os niveis.
<p align="center">
  <img src="https://github.com/katherinGriffi/M-todos_extra-o_outliers/blob/main/estadisticas_2dometodo.JPG" width=80% height=80%>  
 </p>

##### Este método envolve a média e o desvio padrão, se houver outliers extremos, especialmente em distribuição assimétricas como as que temos, pode afetar significativqamente a estimação dos parametros.
##### Este método e recomendável em distribuições normais.



# 3er Método - Isolation Forest
É um algoritmo de machine learning usado para deteção de anomalias. Este modelo é baseado em particiones recursivas dos dados, para isolar anomalias.

<p align="center">
  <img src="https://github.com/katherinGriffi/M-todos_extra-o_outliers/blob/main/IsolationForest.JPG" width=40% height=40%>  
</p>



# 4to Método - K_NN (k-Nearest Neighbors)


<p align="center">
  <img src="https://github.com/katherinGriffi/M-todos_extra-o_outliers/blob/main/knn.png" width=40% height=40%>  
</p>
