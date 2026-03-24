# Redes Neurais Artificiais - Modelagem com Adaline

O objetivo principal é utilizar o modelo neural **Adaline** (Adaptive Linear Neuron) para modelar a transformação de um sinal senoidal em um sistema univariado.

## 🎯 Objetivo 

Um sistema transforma um sinal senoidal de entrada em um sinal senoidal de saída com características diferentes. A tarefa é aproximar essa transformação utilizando um modelo linear da forma:

$$y = a + b \cdot x$$

Onde:
* $y$ é o sinal de saída previsto.
* $x$ é o sinal de entrada.
* $a$ representa o *bias* (viés) da rede.
* $b$ representa o peso sináptico associado à entrada.

* De uma forma mais simples:
Você tem uma "caixa preta" (um sistema). Quando você joga um sinal de onda nela (a entrada $x$), ela cospe uma onda um pouco diferente do outro lado (a saída $y$).Você desconfia que a regra matemática que essa caixa está usando para transformar o sinal é uma equação de reta super simples: $y = a + b * x$.
O seu problema é: Você não sabe quais são os números $a$ e $b$.

## 📁 Estrutura de Arquivos

O projeto requer os seguintes arquivos de dados organizados dentro de uma pasta chamada `dados/`:

* [cite_start]`dados/Ex1_t`: Tempos de amostragem dos sinais.
* [cite_start]`dados/Ex1_x`: Valores do sinal de entrada ($x$).
* [cite_start]`dados/Ex1_y`: Valores do sinal de saída ($y$)].
* `Exercicio_Adaline.r`: Script R principal contendo a função de treinamento e a rotina de testes.

## 🚀 Como Executar

1. Certifique-se de ter o ambiente **R** instalado (recomenda-se o uso do RStudio ou VS Code com a extensão R).
2. Garanta que o seu diretório de trabalho (Working Directory) esteja configurado para a pasta raiz onde o script `Exercicio_Adaline.r` se encontra (um nível acima da pasta `dados/`).
3. Execute o script completo.

## 🧠 Detalhes da Implementação

O script realiza as seguintes etapas operacionais:

1.  **Leitura dos Dados:** Importa as matrizes de tempo, entrada e saída, considerando que os arquivos possuem cabeçalho (`header = TRUE`).
2.  **Separação de Dados:** Divide aleatoriamente o conjunto de dados em **70% para treinamento** e **30% para teste**, permitindo a avaliação do modelo com dados não vistos durante o ajuste dos pesos.
3.  **Treinamento:** Utiliza a função customizada `trainadaline` baseada no gradiente descendente estocástico (LMS - Least Mean Squares). O parâmetro `par = 1` é ativado para incluir o cálculo automático do *bias* (coeficiente $a$).
4.  **Avaliação Visual:** Gera dois gráficos:
    * **Curva de Aprendizado:** Mostra o decaimento do erro quadrático ao longo das épocas de treinamento.
      **Teste (Original vs. Previsto):** Compara os pontos do sinal original com a curva prevista pela rede Adaline para o conjunto de testes.

## 📊 Resultados Esperados

Ao final da execução, o console do R exibirá os coeficientes $a$ e $b$ encontrados pelo modelo. O gráfico gerado deve demonstrar a convergência do erro para próximo de zero e uma sobreposição quase perfeita entre os dados de teste originais e a linha de predição gerada pela rede, validando a capacidade de generalização do modelo Adaline para este problema linear.
