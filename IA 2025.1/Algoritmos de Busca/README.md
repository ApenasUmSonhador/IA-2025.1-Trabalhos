# Relatório: Comparação de Algoritmos de Busca em Grafos

## Introdução

Este relatório apresenta a implementação e comparação de quatro algoritmos clássicos de busca em grafos: **Busca em Largura (BFS)**, **Busca de Custo Uniforme (UCS)**, **Busca Gulosa (Greedy)** e **A\***. O objetivo é encontrar o melhor caminho entre dois vértices em um grafo ponderado, analisando o custo, número de nós expandidos e tempo de execução de cada algoritmo.

---

## Estrutura do Grafo

O grafo é representado utilizando a biblioteca `networkx`, com vértices nomeados de 'A' a 'H' e arestas ponderadas. Uma heurística é definida para os algoritmos informados (Greedy e A\*).

```python
arestas = [
    ('A', 'B', 3), ('A', 'C', 5), ('A', 'D', 2), ('A', 'H', 10),
    ('B', 'C', 5), ('B', 'D', 8), ('B', 'E', 4), ('B', 'G', 3), ('B', 'H', 6),
    ('C', 'E', 1), ('C', 'F', 7), ('C', 'G', 9),
    ('D', 'E', 12), ('D', 'H', 14),
    ('E', 'G', 15),
    ('F', 'H', 9),
    ('G', 'H', 3),
]
```

## Algoritmos Implementados

- **BFS (Busca em Largura):** Explora o grafo por níveis, sem considerar pesos das arestas.
- **UCS (Busca de Custo Uniforme):** Expande sempre o nó de menor custo acumulado.
- **Greedy (Busca Gulosa):** Expande o nó com menor valor heurístico, sem considerar o custo real do caminho.
- **A\*:** Combina o custo acumulado e a heurística para escolher o próximo nó a expandir.

Cada algoritmo retorna o caminho encontrado, o custo total, o número de nós expandidos e o tempo de execução.

## Comparação dos Algoritmos

A função `comparar_algoritmos` executa todos os algoritmos para um par de vértices e apresenta os resultados em uma tabela, além de exibir visualmente os caminhos encontrados em cada algoritmo.

Exemplo de saída da tabela:

+-----------+-----------+-------+----------------+-----------+
| Algoritmo |  Caminho  | Custo | Nós Expandidos | Tempo (s) |
+-----------+-----------+-------+----------------+-----------+
|    BFS    | A → B → G |   6   |       9        |  0.000151 |
|    UCS    | A → B → G |   6   |       6        |  0.000152 |
|   Greedy  | A → B → G |   6   |       15       |  0.000129 |
|     A*    | A → B → G |   6   |       9        |  0.000119 |
+-----------+-----------+-------+----------------+-----------+

> **Obs:** Os valores são ilustrativos. Os resultados reais dependem da execução.

## Visualização

O código utiliza `matplotlib` e `networkx` para desenhar o grafo e destacar os caminhos encontrados por cada algoritmo, facilitando a comparação visual.

## Conclusão

- **BFS** não considera pesos, podendo não encontrar o caminho de menor custo em grafos ponderados.
- **UCS** sempre encontra o caminho de menor custo, mas pode expandir mais nós.
- **Greedy** é rápido, mas pode não encontrar o caminho ótimo.
- **A\*** geralmente expande menos nós que UCS e encontra o caminho ótimo, desde que a heurística seja admissível.

A escolha do algoritmo depende do problema, do tamanho do grafo e da qualidade da heurística.

---

## Referências

- [NetworkX Documentation](https://networkx.org/)
- [Algoritmos de Busca - Wikipedia](https://pt.wikipedia.org/wiki/Algoritmo_de_busca)
- [A* Search Algorithm](https://en.wikipedia.org/wiki/A*_search_algorithm)