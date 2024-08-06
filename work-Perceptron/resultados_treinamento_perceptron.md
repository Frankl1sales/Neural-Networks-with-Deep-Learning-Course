# Resultados do Treinamento do Perceptron

Neste documento, apresentamos os resultados do treinamento de um modelo Perceptron para classificação de óleo em duas classes de pureza: {P1, P2}. O treinamento foi realizado usando a regra de Hebb com uma taxa de aprendizagem de 0,01. O conjunto de dados de treinamento contém medições de três grandezas físico-químicas do óleo.

## Tabela de Resultados

| Treinamento | Peso Inicial w0 | Peso Inicial w1 | Peso Inicial w2 | Peso Final w0 | Peso Final w1 | Peso Final w2 | Número de Épocas |
|--------------|------------------|------------------|------------------|---------------|---------------|---------------|------------------|
| 1            | -0.5095548       | -0.7187625       | 0.086689234      | -0.60433054    | -0.46541575   | -0.15917638   | 100              |
| 2            | -0.82025856      | 0.9834243        | 0.32081985       | -0.86179906    | 1.1189632     | 0.14887491    | 100              |
| 3            | -0.8649089       | -0.08755267      | -0.67385525      | -0.8038232     | 0.3119251     | -0.69978863   | 100              |
| 4            | -0.89733833      | 0.1662054        | -0.008985519     | -0.84765804    | 0.54376554    | -0.07711062   | 100              |
| 5            | 1.1651448        | 0.13767481       | -1.0352745       | 0.98673004     | 0.57722163    | -1.2912569    | 100              |

## Análise dos Resultados

### Pesos Iniciais e Finais

- **Pesos Iniciais**: Cada execução do treinamento inicia com pesos aleatórios para `w0`, `w1` e `w2`. Isso é feito para garantir que o modelo não esteja sujeito a um viés inicial e possa explorar diferentes caminhos durante o treinamento.
- **Pesos Finais**: Os pesos finais após 100 épocas variam consideravelmente entre os treinamentos, refletindo a influência dos pesos iniciais e as mudanças no modelo durante o treinamento.

### Número de Épocas

- **Constante**: O número de épocas foi fixado em 100 para todos os treinamentos. Isso garantiu que cada execução tivesse o mesmo número de atualizações de peso, permitindo uma comparação justa entre os diferentes treinamentos.

### Observações

1. **Variabilidade dos Pesos**: A variabilidade dos pesos finais entre os treinamentos indica que o modelo está explorando diferentes configurações de peso baseadas nas inicializações aleatórias. Isso é esperado e pode afetar a performance do modelo em termos de capacidade de generalização.

2. **Convergência**: A convergência para pesos finais específicos depende da combinação dos pesos iniciais e das atualizações durante o treinamento. É possível que diferentes inicializações possam levar a diferentes pesos finais, mas todos com um número fixo de épocas.

3. **Avaliação da Performance**: Para uma análise mais completa, seria útil incluir métricas de desempenho, como acurácia, para verificar a eficácia do modelo em cada treinamento.

## Conclusão

Os resultados mostram a eficácia do treinamento do Perceptron com a regra de Hebb e fornecem uma visão sobre como a inicialização dos pesos pode influenciar o desempenho do modelo. Experimentos adicionais podem incluir variações na taxa de aprendizagem, diferentes números de épocas, e a adição de métricas de avaliação para uma análise mais abrangente.


