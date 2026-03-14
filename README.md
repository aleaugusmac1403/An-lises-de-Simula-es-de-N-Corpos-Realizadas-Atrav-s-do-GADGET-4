# Análise Dinâmica de Galáxias Interagentes (GADGET-4)

Este repositório contém os algoritmos em **Python** (no formato *Jupyter Notebook*) desenvolvidos para a extração, processamento e visualização de dados oriundos de simulações hidrodinâmicas de N-Corpos realizadas com o código **GADGET-4**. 

O código aqui disponibilizado foi construído como parte metodológica e analítica da dissertação de mestrado: *"Dinâmica dos Pares de Galáxias Interagentes AM 2058-381 e AM 1228-260 Via Simulações de N-Corpos"* (Universidade do Vale do Paraíba - UNIVAP).

## 🚀 Funcionalidades

O *notebook* principal (`GADGET-4 Analises.ipynb`) concentra toda a rotina pós-simulação:

1. **Leitura de *Snapshots*:** Utilização da biblioteca `unsio` para ler os *outputs* do GADGET-4 e extrair vetores de posição, velocidades, massas e IDs das partículas discretizadas (Bojo, Disco, Gás, Halo, Estrelas).
2. **Centralização Dinâmica:** Implementação combinada do algoritmo **K-Means** (para segregação espacial inicial dos núcleos) e da técnica **Shrinking Sphere** (Esfera Encolhedora) para determinar com precisão os centros dos poços de potencial gravitacional durante a fase de fusão.
3. **Análise Cinemática:** - Cálculo das Curvas de Rotação ($V_{circ}$) com base na massa interna em cascas esféricas.
   - Obtenção dos Perfis de Velocidade Radial (PVRs) aplicando rotinas matemáticas de alinhamento de eixos (*Position Angles* - PA) e fendas espectroscópicas virtuais para comparação direta com os dados observacionais do telescópio Gemini.
4. **Análise Morfológica e Termodinâmica:**
   - Criação de mapas de densidade bidimensionais e mapas de velocidade (Momentos 0, 1 e 2 da Equação de Vlasov).
   - Acompanhamento da evolução secular vs. colisional através da Taxa de Formação Estelar (SFR).
   - Aplicação da Função Inicial de Massa (IMF) de Kroupa (2001) para dissecar a demografia estelar gerada pelos *starbursts*.

## 🛠️ Tecnologias e Bibliotecas

O ambiente de análise depende das seguintes ferramentas:

* **Python 3.x**
* **Jupyter Notebook**
* `unsio` (Leitura universal e manipulação de arquivos de N-Corpos)
* `numpy` & `scipy` (Cálculo numérico, integração paramétrica e otimização)
* `scikit-learn` (Modelagem de proximidade via *KDTree* e agrupamento via *KMeans*)
* `matplotlib` (Construção de gráficos, histogramas e projeções visuais 2D)
* `opencv-python` (Processamento digital de *frames*)

## ⚙️ Como Utilizar

1. Certifique-se de que os pacotes citados acima estão instalados no seu ambiente (ex: `pip install numpy scipy matplotlib scikit-learn opencv-python jupyter`).
2. É necessário ter a base `unsio` configurada corretamente no sistema operacional.
3. Atualize os caminhos (`paths`) de leitura dos *snapshots* dentro do *notebook* para apontar para o seu diretório local.
4. Execute as células em sequência para processar e extrair os painéis gráficos (ex: visualização do "Snap: 092" de AM 2058-381).

## 📄 Licença
Licença MIT - Sinta-se livre para utilizar, modificar e adaptar este código para os seus estudos em astrofísica computacional, lembrando de citar o trabalho de origem.
