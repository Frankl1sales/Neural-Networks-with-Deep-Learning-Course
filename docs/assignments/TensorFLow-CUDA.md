# Configuração do Ambiente para CUDA e TensorFlow

Este documento fornece instruções para configurar um ambiente de desenvolvimento com CUDA e TensorFlow. 

## Requisitos

- Ubuntu 20.04 ou superior
- NVIDIA GPU com suporte CUDA
- Conda

## 1. Instalando CUDA

1. **Instale o Driver NVIDIA:**

   Primeiro, certifique-se de que você tem o driver NVIDIA instalado. Você pode instalar o driver usando o seguinte comando:

   ```bash
   sudo apt update
   sudo apt install nvidia-driver-525
   ```

   Substitua `525` pela versão mais recente do driver se necessário.

2. **Instale o CUDA Toolkit:**

   Instale o CUDA Toolkit usando o seguinte comando:

   ```bash
   sudo apt install nvidia-cuda-toolkit
   ```

3. **Configure as Variáveis de Ambiente:**

   Após a instalação, configure as variáveis de ambiente para CUDA. Adicione as seguintes linhas ao final do arquivo `~/.bashrc`:

   ```bash
   export CUDA_HOME=/usr/lib/nvidia-cuda-toolkit
   export LD_LIBRARY_PATH=$CUDA_HOME/lib64:$LD_LIBRARY_PATH
   ```

   Depois, atualize o terminal com:

   ```bash
   source ~/.bashrc
   ```

4. **Verifique a Instalação do CUDA:**

   Verifique se o CUDA está corretamente instalado e configurado:

   ```bash
   nvcc --version
   ```

## 2. Configurando o TensorFlow com Conda

1. **Crie um Novo Ambiente Conda:**

   Crie e ative um novo ambiente Conda para o projeto:

   ```bash
   conda create -n RNA python=3.12
   conda activate RNA
   ```

2. **Instale TensorFlow:**

   Use o `pip` para instalar a versão mais recente do TensorFlow. Se você estiver usando CUDA, a instalação do TensorFlow incluirá suporte a GPU automaticamente:

   ```bash
   pip install tensorflow
   ```

   Caso precise de uma versão específica, ajuste o comando para incluir a versão desejada, por exemplo:

   ```bash
   pip install tensorflow==2.13.0
   ```

3. **Verifique a Instalação do TensorFlow:**

   Após a instalação, verifique a versão do TensorFlow para garantir que foi instalado corretamente:

   ```bash
   python -c "import tensorflow as tf; print(tf.__version__)"
   ```

## 3. Teste de Compatibilidade

Para garantir que TensorFlow pode usar a GPU com CUDA, execute o seguinte script Python:

```python
import tensorflow as tf

print("Num GPUs Available: ", len(tf.config.list_physical_devices('GPU')))
```

Se o script retornar o número de GPUs disponíveis, sua configuração está correta.

## Problemas Comuns

- **TensorFlow não detecta GPU:** Certifique-se de que as variáveis de ambiente estão corretamente configuradas e que a versão do TensorFlow é compatível com sua versão do CUDA.
- **Erro ao instalar pacotes:** Verifique se todos os comandos foram executados no ambiente Conda ativo e se você tem as permissões necessárias para instalar pacotes.

Para mais detalhes, consulte a [documentação oficial do TensorFlow](https://www.tensorflow.org/install) e [documentação do CUDA](https://docs.nvidia.com/cuda/).

