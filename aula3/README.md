# Perceptron Neural Network Project

Este projeto implementa uma rede neural para realizar a classificação binária usando dados de um arquivo Excel. A rede neural é construída com TensorFlow e Keras, e o projeto inclui etapas de pré-processamento de dados, treinamento do modelo, e avaliação do desempenho.

## Pré-requisitos

Certifique-se de ter as seguintes bibliotecas Python instaladas:

- `tensorflow`
- `numpy`
- `matplotlib`
- `pandas`
- `scikit-learn`

Você pode instalar essas dependências usando o pip:

```bash
pip install tensorflow numpy matplotlib pandas scikit-learn
```

## Estrutura do Projeto

- **Tabela_Perceptron.xls**: Arquivo Excel contendo os dados para o treinamento.
- **main.py**: Script principal que carrega os dados, treina a rede neural e avalia o modelo.

## Passos do Projeto

1. **Carregamento dos Dados**: O script carrega os dados do arquivo Excel `Tabela_Perceptron.xls` e os exibe para verificação.

2. **Preparação dos Dados**: Os dados são separados em features (X) e labels (y). As labels são convertidas para uma representação binária (0 e 1).

3. **Divisão dos Dados**: O conjunto de dados é dividido em conjuntos de treino e teste. Os dados também são normalizados usando `StandardScaler`.

4. **Construção do Modelo**: O modelo de rede neural é construído usando a API `Sequential` do Keras. Ele consiste em:
   - Uma camada oculta com 512 neurônios e função de ativação ReLU.
   - Um Dropout para evitar overfitting.
   - Uma segunda camada oculta com 1024 neurônios e função de ativação Tanh.
   - Uma camada de saída com um neurônio e função de ativação Sigmoid para classificação binária.

5. **Compilação e Treinamento**: O modelo é compilado com o otimizador Adam e a função de perda `binary_crossentropy`. O treinamento é realizado por 20 épocas com validação nos dados de teste.

6. **Avaliação e Visualização**: Após o treinamento, o modelo é avaliado nos dados de teste e a acurácia é impressa. Além disso, são plotadas as curvas de perda e acurácia ao longo das épocas.

## Como Executar

1. Certifique-se de que o arquivo `Tabela_Perceptron.xls` está na mesma pasta que o script.
2. Execute o script Python:

```bash
python main.py
```

3. O script exibirá os dados carregados, treinará a rede neural, avaliará o modelo e exibirá gráficos de perda e acurácia.

## Resultados

Após o treinamento, a rede neural atinge uma acurácia de aproximadamente **X%** nos dados de teste. Os gráficos de perda e acurácia ao longo das épocas ajudam a visualizar o desempenho do modelo durante o treinamento e validação.

