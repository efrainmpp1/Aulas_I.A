# Introdução à Rede Neural SOM (Self-Organizing Map)

## O que é uma Rede Neural SOM?

A Self-Organizing Map (SOM) é um tipo de rede neural não supervisionada introduzida por Teuvo Kohonen na década de 1980. SOMs são usadas principalmente para visualização e clusterização de dados de alta dimensão, transformando-os em um espaço de baixa dimensão (geralmente 2D) preservando as relações topológicas dos dados originais.

## Objetivo

O principal objetivo de uma SOM é mapear dados multidimensionais para um grid bidimensional de neurônios, onde cada neurônio representa um cluster de dados similares. Isso facilita a visualização de padrões e agrupamentos dentro dos dados.

## Conceitos Básicos

### Estrutura

- **Neurônios**: Unidades básicas da SOM, organizadas em um grid geralmente 2D.
- **Grid**: Estrutura bidimensional onde os neurônios são dispostos. Cada neurônio possui um vetor de pesos de mesma dimensão que os dados de entrada.

### Funcionamento

1. **Inicialização**:
   - Os pesos dos neurônios são inicializados aleatoriamente ou usando métodos específicos.
2. **Fase de Treinamento**:
   - Para cada dado de entrada:
     - **Encontrar o Neurônio Vencedor (BMU - Best Matching Unit)**: O neurônio cujo vetor de pesos é mais próximo ao dado de entrada.
     - **Atualizar Pesos**: Ajustar os pesos do BMU e seus neurônios vizinhos para que se aproximem mais do dado de entrada.
     - A atualização dos pesos é governada por uma função de vizinhança que diminui ao longo do tempo.

### Parâmetros Importantes

- **Tamanho do Grid**: Número de neurônios em cada dimensão do grid.
- **Taxa de Aprendizado**: Determina o quanto os pesos dos neurônios são ajustados em cada iteração.
- **Raio de Vizinhança**: Define a área ao redor do BMU que será afetada durante a atualização dos pesos.

## Aplicações

- **Visualização de Dados**: Transformar dados de alta dimensão em mapas bidimensionais fáceis de interpretar.
- **Clusterização**: Identificar grupos de dados similares.
- **Redução de Dimensionalidade**: Simplificar conjuntos de dados complexos mantendo as relações topológicas.
