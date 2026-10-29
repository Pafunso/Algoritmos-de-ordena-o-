# Controle de Estoque com Bubble Sort e Quick Sort

Atividade avaliativa de Algoritmos de Ordenação, desenvolvida em linguagem C.

Aluno: Caetano
Disciplina: Algoritmos e Pensamento Computacional 
Professora: Karla

## Objetivo

Fazer um programa em C que ordena uma lista de produtos pela quantidade em estoque, usando dois algoritmos diferentes (Bubble Sort e Quick Sort) sobre os mesmos dados, e mostrar quanto trabalho cada um precisou para chegar ao mesmo resultado.

## Situação-problema

Em um mercadinho, o dono não consegue olhar a lista inteira de produtos todo dia para descobrir o que está acabando. Se a lista estiver ordenada da menor quantidade para a maior, os produtos que precisam ser repostos primeiro ficam logo no começo.

O programa trabalha com 12 produtos, cada um com nome, quantidade em estoque e preço. Ele mostra a lista como foi cadastrada, ordena com cada algoritmo, mostra o resultado e no final avisa quais são os 3 produtos mais urgentes para repor.

## Como executar

Precisa de um compilador C, como o GCC.

```
gcc main.c -o ordenacao
./ordenacao
```

No Windows o executável gerado é `ordenacao.exe`.

## Exemplo de saída

Depois da ordenação (menor para maior quantidade), os dois algoritmos chegam à mesma lista:

| # | Produto         | Quantidade |
|---|-----------------|-----------|
| 1 | Sabao em po     | 5         |
| 2 | Cafe 500g       | 7         |
| 3 | Feijao 1kg      | 12        |
| 4 | Biscoito        | 18        |
| 5 | Oleo de soja    | 21        |
| 6 | Sal 1kg         | 27        |
| 7 | Acucar 1kg      | 33        |
| 8 | Molho de tomate | 39        |
| 9 | Arroz 5kg       | 45        |
| 10 | Macarrao 500g  | 60        |
| 11 | Leite 1L       | 80        |
| 12 | Papel higienico | 90        |

Para esse conjunto de dados, o programa contou:

| Algoritmo   | Comparações | Trocas |
|-------------|-------------|--------|
| Bubble Sort | 60          | 32     |
| Quick Sort  | 28          | 26     |

Com só 12 itens a diferença é pequena, mas já dá para ver que o Quick Sort compara menos.

## Como os algoritmos funcionam

### Bubble Sort

Percorre a lista comparando cada elemento com o vizinho da direita. Se estiverem fora de ordem, troca os dois. Ao fim de uma passada completa, o maior elemento já está na última posição, então a próxima passada pode parar uma casa antes. Se uma passada inteira não fizer nenhuma troca, a lista já está ordenada e o algoritmo para.

Exemplo com `[5, 2, 9, 1]`:

- 1ª passada: `[2, 5, 1, 9]`
- 2ª passada: `[2, 1, 5, 9]`
- 3ª passada: `[1, 2, 5, 9]`

Na prática, ele faz cerca de n² comparações no pior caso, por isso fica lento em listas grandes. Em compensação, o código é bem simples.

### Quick Sort

Escolhe um elemento como pivô (neste código, o último da parte que está sendo ordenada). Depois organiza a lista de forma que os valores menores ou iguais ao pivô fiquem à esquerda e os maiores à direita, deixando o pivô na posição final dele. Em seguida repete o mesmo processo, de forma recursiva, na parte da esquerda e na parte da direita. Quando sobra um trecho com 0 ou 1 elemento, não há mais o que ordenar.

Exemplo com `[5, 2, 9, 1]`, pivô = 1:

- Todos os outros são maiores que 1, então o pivô vai para o começo: `[1, 2, 9, 5]`
- Sobra ordenar `[2, 9, 5]` com pivô 5, que resulta em `[2, 5, 9]`
- Lista final: `[1, 2, 5, 9]`

Na média faz cerca de n·log n comparações, o que é bem menos que o Bubble Sort. No pior caso (por exemplo, lista já ordenada com pivô sempre no último elemento) também chega a n².

## Arquivos

- `main`: código-fonte, com comentários explicando cada algoritmo
- `README.md`: este arquivo
- 
