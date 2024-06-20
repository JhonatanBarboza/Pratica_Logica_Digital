# Pratica Logica Digital
Descrição
# Projeto 3: Robô Móvel
Este projeto implementa um sistema de controle para um robô móvel usando a placa DE0-CV com FPGA Cyclone V. Utiliza três sensores de proximidade (direita, frente e esquerda) e três comandos de deslocamento correspondentes. A lógica de controle, baseada nas leituras dos sensores, define os comandos de movimento para garantir uma navegação eficiente e evitar obstáculos. 

##[Descrição do Projeto](https://github.com/user-attachments/files/15919390/robo-movel-4-5.pdf)

### Sistema de Comandos
Os comandos do robô são definidos pelas seguintes expressões lógicas baseadas nos estados dos sensores:

1. **Comando Direita (CD):** ((E+F)+D)*(E+F+D)*((!D*E)+F) 

4. **Comando Frente (CF):** !F

5. **Comando Esquerda (CE):** CE = (F + D) + !E 

### Lógica de Operação
1. **Frente (CF):** Quando o sensor **F** não estiver acionado !F, o comando de frente será acionado, independentemente dos outros sensores.
2. **Esquerda (CE):** Quando os sensores **D** e **F** estiverem acionados D + F ou **E** não estiver acionado !E, o comando esquerda será acionado.
3. **Direita (CD):** O comando direita será acionado em várias situações:
   - Quando o sensor **E** e **F** estiverem acionados.
   - Quando os sensores **D** e **F** estiverem acionados.
   - Quando apenas o sensor **F** estiver acionado.
   - Quando os sensores **E**, **D** e **F** estiverem acionados.

### Resumo das Condições
- **Frente (CF):** Acionado quando **F** não estiver acionado.
- **Esquerda (CE):** Acionado quando **D** e **F** estiverem acionados ou **E** não estiver acionado.
- **Direita (CD):** Acionado quando **E** e **F** estiverem acionados, quando **D** e **F** estiverem acionados, quando apenas **F** estiver acionado, ou quando **E**, **D** e **F** estiverem acionados.

### Observações
O robô só executa uma tarefa por vez, garantindo que apenas um comando (frente, esquerda ou direita) seja acionado de cada vez com base nas condições dos sensores.
