# Métodos extração de outliers
Neste repositorio realizo a comparação de diferentes métodos para extração de outliers (IQR, Z-Core, Isolation Forest e KNN). Meu objetivo é escolher qual seria o melhor método para o tipo de distribuição de dados.

# Data
Os dados contem o tempo de atendimeto (dias) dos tickets da área de suporte NOC, dividos em L1 (layer 1), L2 (layer2) e Tempo Total que é a soma de L1+L2 de uma empresa fiticia.


# O que são Outliers e para que detetarlos?
Um outlier é uma observação que se diferencia tanto das demais observações que levanta suspeitas de que aquela observação foi gerada por um mecanismo distinto” (Hawkins, 1980)

Detectar outliers é uma etapa crucial na análise de dados, pois ajuda a garantir a integridade, precisão e confiabilidade das conclusões derivadas dos dados

# Nossos dados:
No histograma abaixo podemos ver a distribuição de nosso dados para L1, L2 e Suporte.

<p align="center">
  <img src=" https://github.com/katherinGriffi/M-todos_extra-o_outliers/blob/main/Histograma-original.png" width=80% height=80%>
 </p>

