# Relatório: Otimização Local com Hill Climbing

## 1. Introdução

Este relatório apresenta a aplicação do algoritmo Hill Climbing para otimização de uma função bidimensional não trivial, utilizando Python e bibliotecas de visualização como Matplotlib e Plotly. O objetivo é analisar o comportamento do algoritmo em diferentes cenários e estratégias, incluindo a versão básica e a abordagem com random restarts.

---

## 2. Descrição da Função

A função utilizada é:

```python
def f(x, y):
    return (x**2) + (y**2) + 25*((np.sin(x))**2 + (np.sin(y)**2))
```

- **Características**: Sempre positiva, com múltiplos mínimos locais e um único mínimo global em (0,0), onde f(0,0) = 0.

---

## 3. Visualização da Função

Foram gerados gráficos 3D e curvas de nível para ilustrar a superfície da função, evidenciando a presença de vários mínimos locais e o mínimo global.

- **Matplotlib**: Superfície 3D e curvas de nível.
- **Plotly**: Gráficos interativos para melhor exploração visual.

---

## 4. Hill Climbing - Versão Básica

### 4.1. Algoritmo

- Inicia em um ponto aleatório.
- Avalia os 8 vizinhos (N, S, L, O, NE, NO, SE, SO).
- Move para o vizinho com menor valor da função.
- Repete até não haver melhora.

### 4.2. Resultados

Foram realizados testes com diferentes pontos iniciais. Em geral, o algoritmo converge rapidamente (menos de 20 iterações) para mínimos locais próximos ao ponto inicial. O tempo de execução é muito baixo (inferior a 1ms).

- **Limitação**: Pode ficar preso em mínimos locais, dependendo do ponto de partida.

---

## 5. Hill Climbing com Random Restarts

### 5.1. Estratégia

Executa o algoritmo básico a partir de vários pontos iniciais aleatórios, retornando o melhor resultado encontrado.

### 5.2. Resultados

- **Vantagem**: Aumenta a chance de encontrar o mínimo global.
- **Desempenho**: Tempos de execução entre 6ms e 18ms para 20 reinícios.
- **Visualização**: Caminhos percorridos por cada reinício podem ser visualizados em animações 3D.

---

## 6. Conclusões

- O Hill Climbing é eficiente para encontrar mínimos locais rapidamente, mas pode não encontrar o mínimo global em funções com muitos mínimos locais.
- A estratégia de random restarts melhora significativamente a robustez do método, aproximando-se mais do mínimo global.
- Visualizações 3D e curvas de nível são fundamentais para entender o comportamento do algoritmo e a topologia da função.

---

## 7. Referências

- Documentação das bibliotecas: [NumPy](https://numpy.org/), [Matplotlib](https://matplotlib.org/), [Plotly](https://plotly.com/python/)
- Conceitos de otimização local e Hill Climbing em IA.
