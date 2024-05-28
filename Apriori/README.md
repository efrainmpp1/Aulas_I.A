# Introdução ao Algoritmo Apriori

## O que é o Algoritmo Apriori?

O algoritmo Apriori é um dos métodos mais conhecidos e amplamente utilizados para mineração de regras de associação em bases de dados transacionais. Ele foi introduzido por Rakesh Agrawal e Ramakrishnan Srikant em 1994 e é usado para identificar conjuntos de itens frequentes e descobrir relações interessantes entre esses itens em grandes bases de dados.

## Objetivo

O principal objetivo do algoritmo Apriori é encontrar associações ou padrões frequentes entre itens em um conjunto de dados transacional. Isso é especialmente útil em análises de mercado, onde se deseja entender quais produtos são frequentemente comprados juntos.

## Conceitos Básicos

### Transações e Itens

- **Transação**: Um conjunto de itens comprados juntos por um cliente em uma única compra. Representada como uma linha em uma base de dados.
- **Item**: Um produto ou serviço incluído em uma transação. Representado como uma coluna em uma base de dados.

### Suporte

- **Suporte**: A frequência de ocorrência de um conjunto de itens em todas as transações.
- **Fórmula**:
  \[
  \text{Suporte}(A) = \frac{\text{Número de transações contendo } A}{\text{Total de transações}}
  \]
- **Exemplo**: Se o conjunto de itens `A = {leite, pão}` aparece em 30 de 100 transações, o suporte de `A` é 0.30 ou 30%.

### Confiança

- **Confiança**: A probabilidade de ocorrência do item consequente dado que o item antecedente ocorre.
- **Fórmula**:
  \[
  \text{Confiança}(A \rightarrow B) = \frac{\text{Suporte}(A \cup B)}{\text{Suporte}(A)}
  \]
- **Exemplo**: Se 20 das 30 transações que contêm `leite` também contêm `pão`, a confiança da regra `leite → pão` é \(\frac{20}{30} = 0.67\) ou 67%.

### Lift

- **Lift**: Medida da importância da regra de associação, que compara a confiança da regra com a frequência esperada do consequente.
- **Fórmula**:
  \[
  \text{Lift}(A \rightarrow B) = \frac{\text{Confiança}(A \rightarrow B)}{\text{Suporte}(B)}
  \]
- **Exemplo**: Um lift maior que 1 indica uma associação positiva entre os itens A e B.

## Funcionamento do Algoritmo Apriori

1. **Geração de Conjuntos de Itens Frequentes**:

   - Inicialmente, conta a frequência de ocorrência de itens individuais e identifica aqueles que atendem ao suporte mínimo.
   - Em seguida, gera conjuntos de itens de tamanho maior e conta suas frequências, repetindo o processo até que não haja mais conjuntos de itens que atendam ao suporte mínimo.

2. **Geração de Regras de Associação**:
   - Para cada conjunto de itens frequentes, gera todas as regras possíveis e calcula sua confiança.
   - Retém apenas as regras que atendem à confiança mínima.

## Exemplo Prático

Vamos considerar um exemplo simples de um mercado com 5 transações:

| Transação | Itens                 |
| --------- | --------------------- |
| 1         | leite, pão, manteiga  |
| 2         | pão, manteiga         |
| 3         | leite, manteiga       |
| 4         | leite, pão            |
| 5         | pão, manteiga, queijo |

### Passo 1: Encontrar Itens Frequentes

- **Suporte mínimo**: 0.4 (40%)

| Item     | Suporte |
| -------- | ------- |
| leite    | 0.6     |
| pão      | 0.6     |
| manteiga | 0.8     |
| queijo   | 0.2     |

Os itens `leite`, `pão` e `manteiga` são frequentes.

### Passo 2: Gerar Regras de Associação

A partir dos itens frequentes, podemos gerar regras como:

- `leite → pão` com confiança 0.5
- `pão → manteiga` com confiança 0.75

## Aplicações do Algoritmo Apriori

- **Análise de Cesta de Compras**: Identificar produtos frequentemente comprados juntos para otimizar layout de loja e promoções.
- **Detecção de Fraude**: Descobrir padrões incomuns em transações financeiras.
- **Recomendação de Produtos**: Sistemas de recomendação em e-commerce.

## Conclusão

O algoritmo Apriori é uma ferramenta poderosa para descobrir padrões ocultos em grandes bases de dados. Ao entender as associações entre itens, empresas podem tomar decisões mais informadas e estratégicas, melhorando suas operações e atendendo melhor seus clientes.
