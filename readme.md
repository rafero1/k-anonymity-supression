# K-Anonimato com Supressão
O objetivo do projeto é realizar a anonimização do dataset de entrada ([Dataset_Covid_CE.csv](Dataset_Covid_CE)) usando um algoritmo k-anonimato com técnica de supressão de valores. 4 versões anonimizadas do dataset foram geradas, para cada valor de k em k = {2, 4, 8, 16}. No final, alguns gráficos foram plotados para ajudar a visualizar a diferença entre os datasets anonimizados para o original.

O projeto foi realizado em python, no ambiente jupyter notebook, e com ajuda das bibliotecas pandas, numpy, itertools e matplotlib.

O algoritmo é extremamente simples. Funcionamento:

1. agrupar registros que já cumprem o valor de k e remover da tabela
1. agrupar registros remanescentes, desconsiderando 1 dos semi-identificadores a fim de criar grupos com >= k membros
1. se conseguir, aplicar supressão no semi-identificador desconsiderado para criar os grupos e removê-los da tabela
1. continuar processo, desconsiderando mais um semi-identificador, até não poder mair desconsiderar ou não sobrar mais registros
1. manualmente suprimir atributos nos registros restantes se necessário