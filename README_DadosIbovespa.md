# Simulação Estocástica do Ibovespa com o Método de Euler-Maruyama em Python 📈🎲

Este repositório apresenta uma aplicação prática de **Finanças Quantitativas**, utilizando a linguagem **Python** para simular trajetórias do índice **Ibovespa**. 

O projeto resolve a Equação Diferencial Estocástica (EDE) do **Movimento Geométrico Browniano (GBM)** por meio do método numérico de **Euler-Maruyama**, permitindo prever múltiplos cenários de mercado (*Random Walkers*) e compará-los diretamente com dados históricos reais da bolsa brasileira.

---

## 🚀 Funcionalidades e Objetivos
* **Modelagem Financeira:** Implementação do Movimento Geométrico Browniano, considerando um parâmetro de tendência/retorno linear ($\mu$) e um parâmetro de volatilidade/ruído estocástico ($\sigma$).
* **Simulação Monte Carlo:** Geração de múltiplos caminhos independentes (*walkers*) baseados em uma caminhada aleatória discreta com probabilidade simétrica de 50% ($r_n = \pm 1$).
* **Validação com Dados Reais:** Processamento e limpeza de dados históricos do arquivo estruturado `IbovData.mat` para sincronização temporal exata com a simulação (janela de 365 dias).

---

## 🛠️ Tecnologias e Dependências
* **Linguagem:** Python 3
* **Bibliotecas Utilizadas:**
  * `numpy`: Vetorização matemática de alta performance, manipulação de matrizes das trajetórias e leitura de dados brutos (`genfromtxt`).
  * `matplotlib`: Renderização de gráficos de séries temporais sobrepostas.

---

## 📊 Estrutura Matemática do Modelo

A variação infinitesimal da cotação $P$ do índice no tempo é governada pela seguinte EDE:

$$dP_n = \mu \cdot P_n \cdot dt + \sigma \cdot P_n \cdot dW_n$$

Onde:
*   $\mu \cdot P_n \cdot dt$ representa o componente determinístico de tendência (*drift*).
*   $\sigma \cdot P_n \cdot dW_n$ representa o componente estocástico de incerteza do mercado (*diffusion*), escalonado por $dW_n = r_n\sqrt{dt}$.

---

## 💻 Como Executar o Projeto

1.  Certifique-se de ter o arquivo de dados `IbovData.mat` no mesmo diretório do notebook.
2.  Instale as dependências executando no seu terminal:
    ```bash
    pip install numpy matplotlib
    ```
3.  Execute o notebook. O programa solicitará parâmetros interativos no terminal:
    *   `Nc`: Número de caminhantes simulados (ex: `3`).
    *   `P0`: Valor inicial da cotação (ex: `10140.05`).
    *   `tf`: Tempo final em dias (ex: `365`).
    *   `dt`: Passo temporal fracionário (ex: `0.00277`).
    *   `mu`: Taxa de retorno esperada.
    *   `sigma`: Coeficiente de volatilidade.
    *   `seed`: Semente para reprodutibilidade estocástica.

---

## 📈 Resultados e Visualizações

O código gera uma série temporal contínua onde as projeções estocásticas dos *walkers* são sobrepostas à linha histórica real do Ibovespa. Essa abordagem visual facilita a análise de sensibilidade dos parâmetros de volatilidade e o estudo de cenários de estresse financeiro.

---

## 📬 Contato

Desenvolvido por **Nicolas Ribeiro Porto**  
* 🏛️ Estudante na USP (Universidade de São Paulo)  
* 📧 E-mail: nicolasrp@usp.br  
* 🔗 [LinkedIn](https://linkedin.com)
