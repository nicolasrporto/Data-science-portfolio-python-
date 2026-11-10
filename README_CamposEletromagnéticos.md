# Eletromagnetismo Numérico: Soluções de Poisson e Biot-Savart em Python 🌌⚡

Este repositório contém uma **plataforma de simulação computacional para problemas clássicos de eletromagnetismo**, desenvolvida em Python. O projeto utiliza métodos numéricos de relaxação e integração iterativa para resolver a Equação de Poisson em sistemas eletrostáticos complexos e calcular o campo magnético gerado por uma espira de corrente.

---

## 🚀 Funcionalidades Principais

O código é dividido em dois módulos físicos de alta precisão:

### 1. Simulador Eletrostático (Equação de Poisson)
*   **Método de Relaxação de Jacobi:** Solução iterativa da equação diferencial parcial de Poisson em uma malha bidimensional discreta.
*   **Dois Cenários de Fronteira:**
    *   **Caso 1:** Carga pontual centralizada em uma caixa quadrada totalmente aterrada ($V = 0$).
    *   **Caso 2:** Carga pontual posicionada estrategicamente entre duas placas paralelas de um capacitor com potenciais fixos ($V = \pm 1$).
*   **Cálculo de Campo Vetorial:** Obtenção das componentes de campo elétrico ($E_x, E_y$) por diferenciação numérica (diferenças centrais).
*   **Análise de Decaimento:** Verificação estatística do decaimento logarítmico do potencial elétrico em duas dimensões ($V(r) = A\ln(1/r) + B$) por meio de ajuste linear polinomial (`polyfit`).

### 2. Simulador Magnetostático (Lei de Biot-Savart)
*   **Integração por Regra de Simpson 1/3:** Método de integração numérica de alta ordem para calcular as componentes tridimensionais ($B_x, B_y, B_z$) do campo magnético.
*   **Espira Circular Discretizada:** Mapeamento vetorial do campo gerado por uma corrente estacionária em qualquer ponto do espaço tridimensional.
*   **Tratamento de Singularidades:** Inclusão de um parâmetro de amortecimento térmico/espacial para evitar divergências infinitas sobre o condutor.

---

## 🛠️ Tecnologias e Dependências

*   **Linguagem:** Python 3
*   **Bibliotecas Científicas:**
    *   `numpy`: Processamento de matrizes multidimensionais e cálculos vetoriais rápidos.
    *   `matplotlib`: Geração de gráficos bidimensionais, mapas de cores, contornos e projeções tridimensionais (3D Quiver).

---

## 📊 Métodos Numéricos Implementados

### Equação de Poisson Discretizada
A aproximação por diferenças finitas para o potencial elétrico $V_{i,j}$ em uma malha com passos $dx$ e $dy$ é resolvida via:

$$V_{i,j} = \frac{(V_{i+1,j} + V_{i-1,j})dy^2 + (V_{i,j+1} + V_{i,j-1})dx^2 + \frac{\rho_{i,j}}{\varepsilon_0}dx^2dy^2}{2(dx^2 + dy^2)}$$

### Integração de Biot-Savart
A contribuição infinitesimal do campo magnético $d\vec{B}$ é integrada ao longo de toda a circunferência utilizando a quadratura de Simpson:

$$\vec{B} = \frac{\mu_0 I}{4\pi} \int_0^{2\pi} \frac{d\vec{\ell} \times \hat{r}}{r^2}$$

---

## 📈 Visualizações Geradas

O script gera automaticamente 4 interfaces gráficas detalhadas:
1.  **Mapas de Cores do Potencial ($V$):** Distribuição bidimensional do potencial usando a escala simétrica `seismic`.
2.  **Linhas de Contorno e Linhas de Campo ($\vec{E}$):** Sobreposição de curvas equipotenciais e vetores de campo elétrico usando a função `quiver`.
3.  **Gráfico de Dispersão $E(r) \times r$:** Demonstração do comportamento físico do campo à medida que a distância radial aumenta.
4.  **Campo Magnético 3D:** Projeção tridimensional dos vetores de indução magnética ao redor da espira circular.

---

## 📂 Como Executar o Projeto

1.  Clone este repositório no seu ambiente local:
    ```bash
    git clone https://github.com
    ```
2.  Instale as dependências necessárias:
    ```bash
    pip install numpy matplotlib
    ```
3.  Execute o script interativo:
    ```bash
    python AtividadeAvaliativa.py
    ```
4.  Insira os parâmetros geométricos e físicos solicitados no terminal (lado da caixa, posição das placas, passo de malha $dx$, coordenadas da carga e intensidade).

---

## 📬 Contato

Desenvolvido por **Nicolas Ribeiro Porto**  
* 🏛️ Estudante de Ciência de Dados e Física Computacional - USP (Universidade de São Paulo)  
* 📧 E-mail: nicolasrp@usp.br  
* 🔗 [LinkedIn](https://linkedin.com)
