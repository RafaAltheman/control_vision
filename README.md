# control_vision

--> Como os motores se comunicam com o robô?

-- O robô possui os motores que são responsáveis por mover as diferentes partes dele. Cada motor é controlado por 3 parametros principais que são: posição, velocidade e torque.

-- Para se comunicar com o robô, utilizamos a biblioteca Dynamixel SDK. Essa biblioteca permite enviar e receber dados dos motores simultaneamente, ou seja, a posição, a velocidade e o torque são definidos para os motores ao mesmo tempo.

-- Para conferir o estado dos motores e fazer as movimentações, abrimos o aplicativo da Dinamyxel para fazer a leitura dos motores, como forma de saber a posição, velocidade e se o torque está ativo ou não. 

-- Cada motor é identificado por um ID, que no caso dos robôs da FEI são classificados de 1 a 16 e suas posições variam de 0 a 2048.

![image](https://github.com/user-attachments/assets/a05a3067-8d8f-4cae-914f-9bd1bad64270)


--> Como funciona a visão do robô?

-- O código da visão usa o modelo YOLOv8 para detectar uma bola e enviar as informações sobre sua posição ao robô. O processo começa com a captura de imagens pela câmera do robô, que são processadas pelo modelo YOLO para identificar a bola. O código então identifica a posição da bola na imagem, determinando se ela está à esquerda, à direita, no centro, ou mais perto ou longe da câmera.

-- Essas informações sobre a posição da bola são publicadas em tópicos ROS2. Dependendo de onde a bola está no campo de visão, o robô pode ajustar suas posições para centralizar a bola (mover pescoço) ou se mover em direção a ela (movimentações). 

-- O código enviar as imagens processadas para um servidor via UDP.

-- Utilizamos o software da Roboflow para "treinar" imagens, com isso um dataset é criado e assim facilita o robô na identificação de cada parte do campo, outros robôs e a bola.

-- Essas informações são enviadas para a decisão que dirá o que deverá ser feito em cada caso.

![image](https://github.com/user-attachments/assets/1b6c03b5-290c-421f-8d1f-dace097bf939)

