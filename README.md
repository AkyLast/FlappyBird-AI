# Flappy Bird com IA

### Visão Geral

Este projeto é uma recriação do famoso jogo Flappy Bird, onde o jogador controla um pássaro que precisa atravessar uma série de canos sem colidir. Além da jogabilidade manual, o código inclui uma inteligência artificial baseada em NEAT que aprende a jogar o jogo de forma autônoma.

### Funcionalidades
- Controle manual do pássaro utilizando a barra de espaço.
- IA que treina e joga automaticamente.
- Gráficos simples e fieis ao estilo do jogo original.
- Exibição da pontuação e da geração atual durante o treino da IA.

### Requisitos
- Python 3.7 ou superior.
- Bibliotecas: `pygame`, `neat-python`.

### Como Executar
1. Clone o repositório:
   ```bash
   git clone https://github.com/seu-usuario/flappy-bird-ia.git
   cd flappy-bird-ia
   ```
2. Instale as dependências:
   ```bash
   pip install -r requirements.txt
   ```
3. Execute o jogo:
   ```bash
   python FlappyBird.py
   ```

### Estrutura do Projeto
- `FlappyBird.py`: Contém a lógica principal do jogo e do treino da IA.
- `imgs/`: Pasta com os recursos gráficos do jogo (fundo, pássaro, canos, chão).
- `config-feedforward.txt`: Arquivo de configuração para o NEAT.

---

## Explicação do Código

### Classes Principais

1. **Passaro**
   - Representa o pássaro no jogo.
   - Controla o movimento, rotação e animação.
   - Métodos principais:
     - `pular()`: Faz o pássaro saltar.
     - `mover()`: Atualiza a posição do pássaro com base na gravidade.
     - `desenhar()`: Renderiza o pássaro na tela.

2. **Cano**
   - Representa os obstáculos no jogo.
   - Controla a posição e verifica colisões com o pássaro.
   - Métodos principais:
     - `definir_altura()`: Define uma altura aleatória para os canos.
     - `mover()`: Move os canos para a esquerda.
     - `colidir()`: Verifica se o pássaro colidiu com o cano.

3. **Chao**
   - Representa o chão do jogo.
   - Controla o movimento para criar a ilusão de deslocamento.

4. **Funções Auxiliares**
   - `ia_jogando = True`: Modo que faz a ia jogar, senão `ia_jogando = False`
   - `desenhar_tela()`: Renderiza todos os elementos do jogo.
   - `tela_game_over()`: Exibe a tela de "Game Over".
   - `main()`: Função principal que gerencia o jogo e o treino da IA.

---

## Explicação da IA

A IA utiliza a biblioteca NEAT (NeuroEvolution of Augmenting Topologies) para treinar redes neurais de forma evolutiva. Aqui estão os principais aspectos:

### Como Funciona
1. **Entrada da Rede Neural**:
   - Posição vertical do pássaro.
   - Distância vertical até o topo do cano mais próximo.
   - Distância vertical até a base do cano mais próximo.

2. **Saída da Rede Neural**:
   - Um único valor que decide se o pássaro deve pular ou não.

3. **Aptidão (Fitness)**:
   - Baseada no tempo que o pássaro sobrevive.
   - Quanto mais tempo o pássaro sobrevive, maior é a pontuação atribuída à sua rede neural.

### Configuração do NEAT
- O arquivo `config.txt` define os parâmetros da evolução, como:
  - Tamanho da população.
  - Número de gerações.
  - Taxa de mutação.

### Treinamento
- A cada geração, o NEAT cria uma população de redes neurais.
- As redes são testadas no jogo, e as melhores são selecionadas para a próxima geração.
- O processo continua até que a IA aprenda a jogar eficientemente.

---

## Melhorias Futuras
- Adicionar múltiplos níveis de dificuldade.
- Melhorar os gráficos e sons do jogo.
- Implementar um sistema de leaderboard para comparar pontuações.

### Contribuições
Sinta-se à vontade para abrir issues e pull requests para melhorias ou correções!

