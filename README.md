# control_vision

--> Como os motores se comunicam com o robô?

-- O robô possui os motores que são responsáveis por mover as diferentes partes dele. Cada motor é controlado por 3 parametros principais que são: posição, velocidade e torque.

-- Para se comunicar com o robô, utilizamos a biblioteca Dynamixel SDK. Essa biblioteca permite enviar e receber dados dos motores simultaneamente, ou seja, a posição, a velocidade e o torque são definidos para os motores ao mesmo tempo.

-- Para conferir o estado dos motores e fazer as movimentações, abrimos o aplicativo da Dinamyxel para fazer a leitura dos motores, como forma de saber a posição, velocidade e se o torque está ativo ou não. 

-- Cada motor é identificado por um ID, que no caso dos robôs da FEI são classificados de 1 a 16 e suas posições variam de 0 a 2048.
