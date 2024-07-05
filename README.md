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

# Projeto 5 e 6: Somador Completo e Somador de Quatro Bits

#### Objetivo:
Projetar e implementar um somador completo e um somador de quatro bits utilizando portas lógicas.

#### Somador Completo (Full Adder):

##### Lógica de Controle:
Um somador completo possui três entradas (A, B e Carry-in) e duas saídas (Sum e Carry-out). As expressões booleanas que determinam as saídas são:

- **Soma (Sum):**
  
$$ \text{Sum} = A \oplus B \oplus \text{Carry-in} $$

- **Carry-out:**

$$ \text{Carry-out} = (A \cdot B) + (\text{Carry-in} \cdot (A \oplus B)) $$

##### Descrição do Sistema:
O somador completo é um bloco fundamental para operações aritméticas em circuitos digitais. Ele soma dois bits (A e B) e um bit de transporte de entrada (Carry-in), gerando um bit de soma (Sum) e um bit de transporte de saída (Carry-out). Este módulo é utilizado como base para construir somadores de maior largura de bits, como o somador de quatro bits.

[Projeto5](https://drive.google.com/file/d/1amc8LAnzvjKIWziw4Zhz9InLjIJsGFiv/view?usp=drive_link)

#### Somador de Quatro Bits:

##### Lógica de Controle:
O somador de quatro bits é composto por quatro somadores completos conectados em série, onde o Carry-out de cada somador é conectado ao Carry-in do próximo somador. 

##### Descrição do Sistema:
O somador de quatro bits é utilizado para somar dois números binários de quatro bits, resultando em um número binário de quatro bits e um Carry-out final. Este somador é implementado utilizando quatro somadores completos em cascata. A arquitetura garante a correta propagação do transporte entre os somadores, permitindo operações aritméticas precisas em sistemas digitais.

[Projeto6](https://drive.google.com/file/d/1ZQyOSJkar6BQnexGBYvxm1zZ0noW9zhK/view?usp=drive_link)

# Projeto 7 e 8: Subtrator Completo e Subtrator de Quatro Bits

#### Objetivo:
Projetar e implementar um subtrator completo e um subtrator de quatro bits utilizando portas lógicas.

#### Subtrator Completo (Full Subtractor):

##### Lógica de Controle:
Um subtrator completo possui três entradas (A, B e Borrow-in) e duas saídas (Difference e Borrow-out). As expressões booleanas que determinam as saídas são:

- **Diferença (Difference):**

$$ \text{Difference} = A \oplus B \oplus \text{Borrow-in} $$

- **Empréstimo (Borrow-out):**

$$ \text{Borrow-out} = (\overline{A} \cdot B) + (\overline{(A \oplus B)} \cdot \text{Borrow-in}) $$

##### Descrição do Sistema:
O subtrator completo é um bloco fundamental para operações aritméticas em circuitos digitais. Ele subtrai dois bits (A e B) e um bit de empréstimo de entrada (Borrow-in), gerando um bit de diferença (Difference) e um bit de empréstimo de saída (Borrow-out). Este módulo é utilizado como base para construir subtratores de maior largura de bits, como o subtrator de quatro bits.

[projeto7](https://drive.google.com/file/d/1JDW4z7ew8VbFddj8wosn6-r6O-uEW-7H/view?usp=drive_link)

#### Subtrator de Quatro Bits com display de 7 segmentos:

##### Lógica de Controle:
O subtrator de quatro bits é composto por quatro subtratores completos conectados em série, onde o Borrow-out de cada subtrator é conectado ao Borrow-in do próximo subtrator.

##### Descrição do Sistema:
O subtrator de quatro bits é utilizado para subtrair dois números binários de quatro bits, resultando em um número binário de quatro bits e um Borrow-out final. Este subtrator é implementado utilizando quatro subtratores completos em cascata. A arquitetura garante a correta propagação do empréstimo entre os subtratores, permitindo operações aritméticas precisas em sistemas digitais.

##### Dica: 
Crie blocos do display de sete segmentos e do subtrator de 1 bit.

[projeto8](https://drive.google.com/file/d/1cDLnJ2DwvvvHsPCmMrWVGv1BA1ZNMy0j/view?usp=drive_link)

# Projeto: Somador-Subtrator de Quatro Bits

#### Objetivo:
Projetar e implementar um circuito combinacional que funcione tanto como somador subtrator de quatro bits, integrando também um sistema para realizar o complemento de dois quando necessário. O circuito é capaz de tratar sinais em paralelo e exibir os resultados em displays de sete segmentos.

#### Lógica de Controle:
O circuito combinacional utiliza o complemento de dois para realizar operações de subtração. A operação a ser realizada (soma ou subtração) é determinada por um sinal de controle (SO). 

##### Função de Controle:
- **SO = 0:** Soma (A + B)
- **SO = 1:** Subtração (A - B)

##### Lógica do Somador-Subtrator:
Para realizar subtrações, o circuito converte o subtraendo B para seu complemento de dois quando SO = 1. Para realizar o complemento de dois, um circuito de portas XOR inverte os bits de B e adiciona um bit de 1.

##### Expressões Booleanas:
Para cada bit \(i\) (de 0 a 3), as expressões booleanas para o somador-subtrator são:

- **Entrada Complementar (B'):**

$$ B_i' = B_i \oplus SO $$

- **Primeiro Bit (LSB):**

$$ S_0 = A_0 \oplus B_0' \oplus SO $$
  
$$ \text{Carry/Borrow}_0 = (A_0 \cdot B_0') + (SO \cdot (A_0 \oplus B_0')) $$

- **Segundo Bit:**

$$ S_1 = A_1 \oplus B_1' \oplus \text{Carry/Borrow}_0 $$

$$ \text{Carry/Borrow}_1 = (A_1 \cdot B_1') + (\text{Carry/Borrow}_0 \cdot (A_1 \oplus B_1')) $$

- **Terceiro Bit:**

$$ S_2 = A_2 \oplus B_2' \oplus \text{Carry/Borrow}_1 $$
$$ \text{Carry/Borrow}_2 = (A_2 \cdot B_2') + (\text{Carry/Borrow}_1 \cdot (A_2 \oplus B_2')) $$

- **Quarto Bit (MSB):**

$$ S_3 = A_3 \oplus B_3' \oplus \text{Carry/Borrow}_2 $$

$$ \text{Carry/Borrow}_3 = (A_3 \cdot B_3') + (\text{Carry/Borrow}_2 \cdot (A_3 \oplus B_3')) $$

- **Bit de Sinal (Overflow):**

$$ S_4 = \text{Carry/Borrow}_3 $$

##### Complemento de Dois:
Se a subtração resulta em um número negativo (quando o minuendo é menor que o subtraendo), o resultado é expresso em complemento de dois. Para isso, um circuito de portas XOR é utilizado para inverter os bits e adicionar 1.

##### Descrição do Sistema:
Este projeto combina lógica booleana e operações aritméticas para implementar um sistema versátil capaz de executar tanto soma quanto subtração, com manipulação adequada de números negativos através do complemento de dois.

[Projeto9](https://drive.google.com/file/d/1vdUv6N4Jz5rGFBBJGZDwv4zn41qlkWbb/view?usp=drive_link)

[Video explicando](https://www.youtube.com/watch?v=A25zZZK6Zug&list=PL400nT9WA9li9LjGXqFKlHqRZxryRAomV&index=8)

# Projeto 10: Multiplicador de Quatro Bits

#### Objetivo:
Projetar e implementar um multiplicador de quatro bits utilizando portas lógicas e registradores para realizar operações de multiplicação binária.

#### Lógica de Controle:
O multiplicador de quatro bits deve multiplicar dois números binários de quatro bits (A3A2A1A0 e B3B2B1B0), resultando em um produto de até oito bits (P7P6P5P4P3P2P1P0).

##### Multiplicação Binária:
A multiplicação binária é realizada de maneira semelhante à multiplicação decimal, com produtos parciais sendo somados. Para um multiplicador de quatro bits, utilizamos a soma dos produtos parciais deslocados de acordo com a posição do bit do multiplicando.

##### Funções Lógicas:
Para cada par de bits dos operandos, a expressão booleana do produto parcial é:

- **Produto Parcial (PP):**

$$ PP_{ij} = A_i \cdot B_j $$

Os produtos parciais são então somados com deslocamentos apropriados para obter o produto final.

##### Circuito de Multiplicação:
1. **Produtos Parciais:**

$$ PP_0 = A_0 \cdot B $$

$$ PP_1 = A_1 \cdot B \ll 1 $$

$$ PP_2 = A_2 \cdot B \ll 2 $$

$$ PP_3 = A_3 \cdot B \ll 3 $$

   Onde ll indica deslocamento à esquerda.

2. **Soma dos Produtos Parciais:**
   - Somar os produtos parciais utilizando somadores binários para obter o produto final:

$$ P = PP_0 + PP_1 + PP_2 + PP_3 $$

##### Descrição do Sistema:
O multiplicador de quatro bits utiliza portas lógicas para calcular os produtos parciais entre cada bit dos operandos. Esses produtos parciais são somados utilizando somadores binários, com deslocamentos apropriados para cada bit de posição. O resultado final é um número binário de até oito bits, representando o produto dos dois números de entrada.

1. **Produtos Parciais:**
   - Para cada bit Bj de B, calcular PPij = Ai*Bj para todos os bits Ai de A.
   - Deslocar cada produto parcial PP ij de acordo com a posição do bit Bj.

2. **Soma dos Produtos Parciais:**
   - Utilizar somadores binários para somar os produtos parciais.
   - Considerar os deslocamentos durante a soma para garantir o alinhamento correto dos produtos parciais.

[projeto10](https://drive.google.com/file/d/1l1AoApyfAxe9YJHgAycaAavxk0nmuTRO/view?usp=drive_link)

[video explicando](https://www.youtube.com/watch?v=5PVTKN-jxA4&list=PL400nT9WA9li9LjGXqFKlHqRZxryRAomV&index=10)




