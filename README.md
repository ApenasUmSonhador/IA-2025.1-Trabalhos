# Projeto-01 Inteligência Artificial

Este repositório reúne dois projetos principais: algoritmos clássicos de busca em grafos ponderados e otimização local com Hill Climbing, ambos implementados em Python com visualizações e comparações de desempenho.

---

## 1. Algoritmos de Busca em Grafos

Implementação e comparação de algoritmos clássicos para encontrar o melhor caminho entre dois nós em um grafo ponderado.

### Algoritmos Implementados

- **BFS (Busca em Largura)**: Explora os nós em camadas, sem considerar pesos.
- **UCS (Uniform Cost Search)**: Busca pelo menor custo acumulado.
- **Greedy (Busca Gulosa)**: Usa uma heurística para escolher o próximo nó.
- **A\***: Combina custo acumulado e heurística para otimizar a busca.

### Estrutura do Grafo

- O grafo é definido por uma lista de arestas ponderadas e representado usando `networkx`.
- Heurísticas são definidas para cada nó, utilizadas nos algoritmos Greedy e A\*.

### Visualização e Comparação

- Caminho encontrado
- Custo total
- Número de nós expandidos
- Tempo de execução
- Resultados apresentados em tabela (`prettytable`) e visualizados graficamente (`matplotlib`), destacando o melhor caminho.

### Como Executar

1. Instale as dependências:
   ```bash
   pip install networkx matplotlib prettytable
   ```
2. Execute o script Python.

#### Exemplo de Uso

```python
comparar_algoritmos('A', 'G')
```

---

## 2. Otimização Local com Hill Climbing

Explora técnicas de otimização local utilizando o algoritmo Hill Climbing para encontrar mínimos de uma função bidimensional.

### Bibliotecas Utilizadas

- `numpy`: operações matemáticas e criação de grids.
- `matplotlib` e `mpl_toolkits.mplot3d`: visualização de superfícies e curvas de nível.
- `plotly`: gráficos interativos 3D.
- `random`: geração de pontos iniciais aleatórios.
- `time`: medição do tempo de execução dos algoritmos.

### Função Otimizada

```python
def f(x, y):
    return (x**2) + (y**2) + 25*((np.sin(x))**2 + (np.sin(y)**2))
```

- Sempre positiva.
- Múltiplos mínimos locais.
- Mínimo global em (0, 0) com valor 0.

### Visualização

- Superfície 3D da função (matplotlib e plotly).
- Curvas de nível (contour plots).
- Caminho percorrido pelo algoritmo Hill Climbing.

### Algoritmo Hill Climbing

- **Versão Básica**: Inicia em ponto aleatório, avalia 8 vizinhos, move para o menor valor, para quando não há melhora.
- **Random Restarts**: Executa múltiplas vezes a partir de diferentes pontos aleatórios, retorna o melhor resultado.
- Visualização dos caminhos dos reinícios, podendo ser animados em 3D.

### Resultados

- O algoritmo básico frequentemente encontra mínimos locais.
- Random restarts aumentam a chance de encontrar o mínimo global.
- Tempos de execução baixos.
- Visualizações facilitam o entendimento do comportamento do algoritmo.

### Como Executar

1. Instale as dependências:
   ```bash
   pip install numpy matplotlib plotly
   ```
2. Execute o notebook ou scripts Python conforme desejado.

---

## Conclusão

Os algoritmos de busca em grafos e otimização local apresentados são ferramentas fundamentais para problemas de caminhos mínimos e otimização. Visualizações e comparações práticas auxiliam no entendimento do comportamento e limitações de cada abordagem.

---

## Autores:

- [Arthur Vinicius Carneiro Nunes](https://github.com/ApenasUmSonhador) - Documentação
- [Francisco Lemuel Ferreira Lima](https://github.com/sanFranciscoLemuel) - Hill Climbing
- [Maria Eduarda de Sousa Pereira](https://github.com/Git-institucional) - Algoritmos de Busca

## Licença

Este projeto é de uso acadêmico e educacional.
