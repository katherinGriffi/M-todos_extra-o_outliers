# Métodos extração de outliers
Neste repositorio realizo a comparação de diferentes métodos para extração de outliers (IQR, Z-Core, Isolation Forest e KNN). Meu objetivo é escolher qual seria o melhor método para o tipo de distribuição de dados.

## Data
Os dados contem o tempo de atendimeto (dias) dos tickets da área de suporte NOC, dividos em L1 (layer 1), L2 (layer2) e Tempo Total de Suporte é a soma de L1+L2 de uma empresa fiticia.


## O que são Outliers e para que detetarlos?
Um outlier é uma observação que se diferencia tanto das demais observações que levanta suspeitas de que aquela observação foi gerada por um mecanismo distinto” (Hawkins, 1980)

Detectar outliers é uma etapa crucial na análise de dados, pois ajuda a garantir a integridade, precisão e confiabilidade das conclusões derivadas dos dados

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

Na Fig3, realizei o cálculas das estadísticas e tanto em L1, L2 e Suporte podemos observar que a media é maior que a mediana, o que indica que a distribuição esta inclinada a direita (possitivamente assimétrica), a maioria dos dados encontrase a esquerda da media, isso também é possivel obsevar na Fig1. Este tipo de distribuição pode ser afetada por valores extremos.

<p align="center">
<img src="https://github.com/katherinGriffi/M-todos_extra-o_outliers/blob/main/estatisticas-geral.JPG" width=80% height=80%>
</p>

# 1er Método - Itervalo Interquartil

Através desse método, outliers são definidos matematicamente como as observações que estão abaixo (Q1 − 1,5 x IQR) do "bigode inferior" do boxplot ou acima (Q3 + 1,5 x IQR) do "bigode superior" do boxplot.
<p align="center">
  <img src="https://github.com/katherinGriffi/M-todos_extra-o_outliers/blob/main/IQR.JPG" width=40% height=40%>  
</p>


# 2do Método - Z_Core
O método Z-Score (ou escore Z) é uma medida estatística que indica quantos desvios padrão um ponto de dados está da média 
de um conjunto de dados.

##### Z = (X – μ) / σ
– μ é a média do conjunto de dados

– σ é o desvio padrão do conjunto de dados
<p align="center">
  <img src="https://github.com/katherinGriffi/M-todos_extra-o_outliers/blob/main/zcore.JPG" width=40% height=40%>  
</p>




# 3er Método - Isolation Forest
É um algoritmo de machine learning usado para deteção de anomalias. Este modelo é baseado em particiones recursivas dos dados, para isolar anomalias.

<p align="center">
  <img src="https://github.com/katherinGriffi/M-todos_extra-o_outliers/blob/main/IsolationForest.JPG" width=40% height=40%>  
</p>



# 4to Método - K_NN (k-Nearest Neighbors)


<p align="center">
  <img src="https://github.com/katherinGriffi/M-todos_extra-o_outliers/blob/main/knn.png" width=40% height=40%>  
</p>
