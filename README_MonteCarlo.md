# Estimativa do Valor de $\pi$ via Método de Monte Carlo em Python 🎯🎲

Este repositório apresenta uma aplicação prática de **Física Computacional e Cálculo Estocástico**, utilizando o **Método de Monte Carlo** para aproximar o valor da constante matemática $\pi$. 

O projeto explora a convergência estatística e a Lei dos Grandes Números através do comportamento assintótico de duas metodologias probabilísticas diferentes em uma escala logarítmica de sorteios ($N$).

---

## 🚀 Metodologias Implementadas

O experimento baseia-se em sortear pontos aleatórios $(x, y)$ uniformemente distribuídos em um quadrado de lado $L=1$. A área de interesse corresponde ao primeiro quadrante de um círculo unitário inscrito, definido pela condição geométrica:

$$y \leq \sqrt{1 - x^2}$$

### 🔹 Método 1: Abordagem de Acerto ou Erro (Hit-or-Miss)
*   Funciona por amostragem geométrica direta: conta-se a fração de pontos que caem dentro da área do quarto de círculo ($N_{circ}$) em relação ao total de pontos sorteados ($N$).
*   O valor estimado de $\pi$ é dado por: 
    $$\pi \approx 4 \times \frac{N_{circ}}{N}$$

### 🔹 Método 2: Integração pelo Método do Valor Médio
*   Aplica a quadratura Monte Carlo para resolver numericamente a integral definida que representa a área sob a curva do círculo: 
    $$\int_0^1 \sqrt{1-x^2} \, dx = \frac{\pi}{4}$$
*   O algoritmo calcula a média amostral da função $f(x) = \sqrt{1-x^2}$ para estimar o valor esperado e converge mais rapidamente devido às propriedades de redução de variância.

---

## 🛠️ Tecnologias e Bibliotecas
*   **Linguagem:** Python 3
*   **Bibliotecas Utilizadas:**
    *   `numpy`: Vetorização matemática e geração de distribuições uniformes contínuas (`random.uniform`).
    *   `matplotlib`: Plotagem gráfica e análise visual de convergência.

---

## 📈 Análise de Convergência e Resultados

O script executa as estimativas de forma iterativa a cada potência de 10 (variando de $10^1$ até $10^N$), gerando um gráfico comparativo onde as duas curvas convergem assintoticamente para o valor analítico real ($\pi \approx 3.14159265$). O Método do Valor Médio (Método 2) demonstra uma estabilidade numérica superior com menor flutuação estatística em valores baixos de $N$.

---

## 📂 Como Executar o Projeto

1. Certifique-se de ter o Python 3 instalado no seu ambiente.
2. Instale os pacotes necessários:
   ```bash
   pip install numpy matplotlib
   ```
3. Execute o script e insira interativamente o número máximo de sorteios desejado ($N$) e a semente aleatória (`seed`) para reprodutibilidade.

---

## 📬 Contato

Desenvolvido por **Nicolas Ribeiro Porto**  
* 🏛️ Estudante de Ciência de Dados e Física Computacional - USP (Universidade de São Paulo)  
* 📧 E-mail: nicolasrp@usp.br  
* 🔗 [LinkedIn](https://linkedin.com)
