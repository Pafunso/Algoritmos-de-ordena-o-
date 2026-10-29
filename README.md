# Ordenação de Estoque com Bubble Sort e Quick Sort

#Objetivo

Aplicação em C que ordena os produtos de um estoque pela quantidade disponível, usando os algoritmos Bubble Sort e Quick Sort, e compara o número de comparações e trocas de cada um.

#Situação-problema

Um mercadinho precisa saber quais produtos estão acabando. Ordenando o estoque do menor para o maior, os itens que precisam de reposição urgente aparecem no topo da lista. A aplicação usa 12 produtos (nome, quantidade e preço), mostra os dados antes e depois da ordenação e lista os 3 itens mais críticos.

#Como executar

Requisito: compilador GCC.
gcc main.c -o ordenacao
./ordenacao
No Windows: gcc main.c -o ordenacao.exe e depois ordenacao.exe.
Também é possível rodar online colando o main.c em um compilador online como o OnlineGDB.

#Algoritmos

#Bubble Sort
Compara pares de elementos vizinhos e troca quando estão fora de ordem. A cada passada, o maior elemento "sobe" para o final do vetor. Se uma passada não realiza trocas, o algoritmo para. Complexidade: O(n²).
#Quick Sort
Usa "dividir para conquistar": escolhe um pivô, separa os menores à esquerda e os maiores à direita, e repete o processo recursivamente em cada lado. Complexidade: O(n log n) em média e O(n²) no pior caso.
Estrutura
main.c: código-fonte comentado
README.md: este arquivo
