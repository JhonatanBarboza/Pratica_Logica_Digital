# Pratica Logica Digital
Descrição

## Dicas para Utilizar o Quartus

Aqui estão algumas dicas úteis para facilitar o uso do Quartus:

1. **Utilize Fios Wire**: Use fios do tipo wire para conectar diferentes partes do circuito. Isso ajuda a manter o design organizado e facilita a visualização das conexões.

2. **Copia e Cola nos Pinos**: Para agilizar a configuração dos pinos, utilize a função de copiar e colar. Isso é especialmente útil quando você tem múltiplos pinos a serem configurados de forma semelhante, economizando tempo e reduzindo erros.

3. **Simplificação Booleana**: Utilize ferramentas online para simplificação de expressões booleanas, como o site [Boolean Algebra](https://www.boolean-algebra.com/). Isso ajuda a otimizar as expressões lógicas antes de implementá-las no Quartus, tornando o design mais eficiente.

Seguir essas dicas pode melhorar significativamente a sua experiência e eficiência ao trabalhar com o Quartus, facilitando o desenvolvimento de projetos complexos de forma mais organizada e intuitiva.


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
     
[Projeto3](https://drive.google.com/file/d/1TZEfIjE5YjMzUMGG7OkXJ11QpQRmGR6_/view?usp=drive_link)
