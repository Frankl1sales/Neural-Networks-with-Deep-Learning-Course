# Projeto Perceptron com TensorFlow

Este projeto utiliza o TensorFlow para treinar um modelo de perceptron em um conjunto de dados fornecido em um arquivo XLS. O modelo é treinado várias vezes com diferentes inicializações de pesos e a acurácia é avaliada. Além disso, o projeto inclui a visualização da função de perda e da acurácia durante o treinamento.

## Requisitos

- Python 3.7 ou superior
- TensorFlow 2.x
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Arquivo `Tabela_Perceptron.xls` com os dados

## Instalação

1. **Clone o Repositório:**

   ```bash
   git clone <URL_DO_REPOSITORIO>
   cd <NOME_DO_REPOSITORIO>
   ```

2. **Crie e Ative um Ambiente Conda:**

   ```bash
   conda create -n perceptron python=3.12
   conda activate perceptron
   ```

3. **Instale as Dependências:**

   ```bash
   pip install tensorflow pandas numpy scikit-learn matplotlib
   ```

4. **Configure CUDA (opcional):**

   Se você deseja usar a GPU para acelerar o treinamento, siga as instruções abaixo para configurar o CUDA:

   1. **Instale o CUDA Toolkit:**

      ```bash
      sudo apt update
      sudo apt install nvidia-cuda-toolkit
      ```

   2. **Configure as Variáveis de Ambiente:**

      Adicione as seguintes linhas ao final do arquivo `~/.bashrc`:

      ```bash
      export CUDA_HOME=/usr/lib/nvidia-cuda-toolkit
      export LD_LIBRARY_PATH=$CUDA_HOME/lib64:$LD_LIBRARY_PATH
      ```

      Depois, atualize o terminal com:

      ```bash
      source ~/.bashrc
      ```
   3.**Para saber mais sobre como configurar o TensorFlow e CUDA, veja:**
     [README_CUDA_TENSORFLOW.md](caminho/para/o/diretorio/README_CUDA_TENSORFLOW.md).

## Uso

1. **Prepare os Dados:**

   Certifique-se de que o arquivo `Tabela_Perceptron.xls` está no mesmo diretório que o script Python. O arquivo deve conter as colunas `x1`, `x2`, `x3` e `d`.

2. **Execute o Script:**

   Execute o script Python para treinar o modelo e gerar as visualizações:

   ```bash
   python seu_script.py
   ```

   Substitua `seu_script.py` pelo nome do arquivo onde o código está salvo.

3. **Visualize os Resultados:**

   Após a execução, o script exibirá gráficos da função de perda e da acurácia do modelo. Os pesos e o modelo treinado serão salvos no arquivo `perceptron_model.h5`.

## Código

O script realiza as seguintes etapas:

1. **Leitura dos Dados:**

   O arquivo XLS é carregado usando `pandas` e os dados são extraídos.

2. **Pré-processamento dos Dados:**

   Os dados são divididos em conjuntos de treinamento e teste e padronizados usando `StandardScaler`.

3. **Criação e Treinamento do Modelo:**

   Um modelo de perceptron é criado e treinado usando o TensorFlow. O treinamento é repetido cinco vezes com diferentes inicializações de pesos.

4. **Avaliação do Modelo:**

   A acurácia do modelo é avaliada e impressa. Além disso, a função de perda e a acurácia são plotadas e exibidas.

5. **Salvar o Modelo:**

   O modelo treinado é salvo no arquivo `perceptron_model.h5`.

## Contribuição

Se você deseja contribuir para este projeto, por favor, siga as etapas abaixo:

1. Fork o repositório.
2. Crie uma nova branch (`git checkout -b feature-nome`).
3. Faça suas alterações e commit (`git commit -am 'Adiciona nova funcionalidade'`).
4. Envie para o branch principal (`git push origin feature-nome`).
5. Abra um Pull Request.
