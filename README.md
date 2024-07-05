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

1. **Comando Direita (CD):** ((E+F)+D)*(E+F+D)*((!D*E)+F 

4. **Comando Frente (CF):**  !F

7. **Comando Esquerda (CE):**  CE = (F + D) + !E

### Lógica de Operação 
1. **Frente (CF):** Quando o sensor **F** não estiver acionado !F, o comando de frente será acionado, independentemente dos outros sensores.
2. **Esquerda (CE):** Quando os sensores **D** e **F** estiverem acionados D + F ou **E** não estiver acionado !E, o comando esquerda será acionado.
3. **Direita (CD):** O comando direita será acionado em várias situações:
   - Quando o sensor **E** e **F** estiverem acionados.
   - Quando os sensores **D** e **F** estiverem acionados.
   - Quando apenas o sensor **F** estiver acionado.
   - Quando os sensores **E**, **D** e **F** estiverem acionados.
     
[Projeto3](https://drive.google.com/file/d/1TZEfIjE5YjMzUMGG7OkXJ11QpQRmGR6_/view?usp=drive_link)


# Projeto 4: Display de 7 Segmentos

#### Objetivo:
Projetar um sistema de controle para um display de 7 segmentos, capaz de mostrar valores em formato hexadecimal a partir de entradas de 4 bits.

#### Lógica de Controle:
Para cada segmento do display (A a G), a lógica booleana que determina seu estado (ligado ou desligado) é dada por:

- **Segmento A:**
  
$$ A = ab'cd + a'b'cd + a'b'c'd + a'bc'd $$
  

- **Segmento B:**
  
$$ B = a'b'cd + acd + abc + ab'd + bc'd $$

- **Segmento C:**
  
$$ C = a'b'c'd + ab'd + abc $$

- **Segmento D:**
  
$$ D = a'b'cd + a'b'c'd + bcd + a'bc'd $$

- **Segmento E:**
  
$$ E = a'b'c + a'b'd + a'cd + b'cd $$

- **Segmento F:**
  
$$ F = a'b'd + a'b'c + a'cd + ab'cd $$

- **Segmento G:**
  
$$ G = a'b'c + ab'c'd + ab'c'd $$

#### Descrição do Sistema:
O sistema recebe como entrada números de 0 a 15 em binário e exibe no display de 7 segmentos o número correspondente em formato hexadecimal. Para isso, as entradas são mapeadas através das funções lógicas acima, garantindo que o display ilumine os segmentos corretos para representar cada dígito hexadecimal (0-9, A-F).

#### Dica:
Utilize Fios Wire.

[Projeto4](https://drive.google.com/file/d/1umWQqudsUT-bZy4cZvuFx8Y1rINWC4JW/view?usp=drive_link)
