# Simulação do Modelo de Ising 1D via Algoritmo de Metropolis (Monte Carlo) 🧲⚛️

Este repositório contém uma implementação computacional avançada em Python para o estudo do **Modelo de Ising Unidimensional (1D)**, um dos pilares da **Física Estatística e Mecânica Quântica** para a descrição de transições de fase e ferromagnetismo em redes de spins.

O simulador utiliza o **Algoritmo de Metropolis-Hastings (Monte Carlo)** acelerado por compilação JIT para calcular a magnetização por spin em função do campo magnético externo, validando os dados numéricos contra a solução teórica exata obtida via **Matriz de Transferência**.

---

## 🚀 Características do Simulador
*   **Dinâmica de Metropolis:** Critério de aceitação estocástica baseado na variação de energia interna ($\Delta E$) provocada por inversões de spin individuais.
*   **Condições de Contorno Periódicas (CCP):** Implementação de uma topologia em anel fechado para mitigar efeitos de borda em uma cadeia finita de $N$ spins.
*   **Aceleração Numérica com Numba:** Uso do decorador `@jit(nopython=True)` para compilação em código de máquina em tempo de execução, otimizando drasticamente os laços iterativos de relaxação térmica.

---

## 🛠️ Tecnologias e Dependências
*   **Linguagem:** Python 3
*   **Bibliotecas Científicas:**
    *   `numpy`: Geração de estados iniciais e amostragem probabilística.
    *   `numba`: Aceleração de hardware e compilação JIT (*Just-In-Time*).
    *   `matplotlib`: Plotagem científica das curvas térmicas.

---

## 📊 Formulação Teórica e Solução Exata

O Hamiltoniano do sistema para uma cadeia com acoplamento ferromagnético de primeiros vizinhos ($J > 0$) e campo magnético externo $h$ é definido por:

$$E = -J \sum_{\langle i,j \rangle} s_i s_j - h \sum_{i} s_i$$

No limite termodinâmico, a magnetização por spin teórica calculada pela Matriz de Transferência assume a forma contínua:

$$m = \frac{\sinh(h/T)}{\sqrt{\sinh^2(h/T) + e^{-4J/T}}}$$

O script executa a simulação variando o campo $h$ sob três patamares térmicos distintos ($T = 0.5$, $T = 1.0$ e $T = 2.0$), comprovando numericamente a ausência de transição de fase espontânea a temperaturas finitas ($T > 0$) no espaço unidimensional, conforme previsto pelo Teorema de van Hove.

---

## 📂 Como Executar o Projeto

1. Clone o repositório e certifique-se de possuir o gerenciador de pacotes `pip`.
2. Instale as dependências executando:
   ```bash
   pip install numpy numba matplotlib
   ```
3. Execute o script ou abra o arquivo no ambiente Jupyter Notebook/Google Colab para visualizar o alinhamento das curvas experimentais pontuais sobre as linhas contínuas analíticas.

---

## 📬 Contato

Desenvolvido por **Nicolas Ribeiro Porto**  
* 🏛️ Estudante de Ciência de Dados e Física Computacional - USP (Universidade de São Paulo)  
* 📧 E-mail: nicolasrp@usp.br  
* 🔗 [LinkedIn](https://linkedin.com)
