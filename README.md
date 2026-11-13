# Teste de Conhecimento 2: K-means manual

Matemática Computacional, Prof. Dr. Alexsandro O. A.
Aluno: Francisco Ferreira da Silva Júnior
Aluno: João Gabriel

## O que foi feito

Implementei as funções do `kmeans_template.py` seguindo o pseudocódigo e o enunciado, usando apenas NumPy, pandas e Matplotlib. As funções são `padronizar`, `centroides_iniciais`, `matriz_distancias`, `atribuir`, `atualizar_centroides`, `calcular_J`, `kmeans` e `silhueta`.

Para rodar, basta deixar os CSV na mesma pasta e executar `python kmeans_template.py`. Os 13 testes do dataset 1 passam e os relatórios dos datasets 2 e 3 são impressos em seguida.


## Discussão: início pelas entregas 3, 4 e 13

Com k = 3 e os centroides iniciais nas entregas 3, 4 e 13, o algoritmo para depois de 6 atualizações com J = 1257,60 e grupos de 10, 38 e 12 entregas, contra J = 230,11 da inicialização padrão.

Isso acontece porque as entregas 3 (3,05; 5,29) e 13 (3,68; 4,73) estão quase no mesmo lugar, na região sudoeste, e a entrega 4 fica no sudeste. Nenhum centroide começa na região norte. Os dois centroides do sudoeste acabam dividindo o mesmo grupo natural, enquanto o terceiro fica com o sudeste e o norte juntos e para no meio do caminho entre os dois. Como cada passo do K-means só diminui J em relação à situação atual, o algoritmo converge para um mínimo local e não sai dele. O K-means não garante a melhor solução, e o resultado depende de onde os centroides começam.

Para evitar, dá para rodar o algoritmo várias vezes com inicializações diferentes e ficar com a de menor J, ou escolher as sementes de forma espalhada, como no K-means++, em que cada novo centroide tende a ser um ponto distante dos que já foram escolhidos. 
