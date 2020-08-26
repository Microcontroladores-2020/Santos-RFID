# Controle de entrada com RFID

## Motivação

A ideia do projeto de controle de acesso por RFID, controlando a abertura de um relé veio da necessidade encotrada no meu dia a dia de possibilitar a entrada de várias pessoas 
na sede da IME Júnior. Atualmente a entrada é controlada por meio de um cadeado de senha, mas por comodidade e também controle seria melhor que ocorrese um registro do momento de entrada das pessoas.
Dessa forma a entrada por meio de RFID foi escolhida por se adequar ao uso do próprio crachá do IME, podendo futuramente evoluir para um sistema com registro de tempo e um banco de dados de crachá maior.


##Escopo do Projeto 

O projeto, nessa versão, implementará a leitura do sensor RFID com a informação de liberação de entrada por meio do acendimento de um LED da Discovey.

## Periféricos utilizados
Para a realização do projeto foi utilizado:
1. Controlador STM32F0;
![STM32F429I-DISCO](https://github.com/Microcontroladores-2020/Santos-RFID/blob/master/imagens/STM32F40.PNG)
2. Sensor RFID-RC522:

![Sensor RFID-RC522](https://github.com/Microcontroladores-2020/Santos-RFID/blob/master/imagens/RFID_RC522.jpg)

A comunicação do sensors foi feita por meio do protocolo de comunicação SPI.

## Pinagem

A pinagem do STM32 foi feita como na imagem a seguir:
![Pinout STM32](https://github.com/Microcontroladores-2020/Santos-RFID/blob/master/imagens/STM32F4.PNG)
 
E com as seguintes funcionalidades:

| Pinos         | Função         | 
| ------------- |:--------------:| 
|      PE2      | SDA RFID       | 
|      PC5      | SCK RFID       |  
|      PA6      | MOSI RFID      |
|      PA7      | MISO RFID      |
|      NC       | IRQ RFID       |
|      PD10     | RST RFID       |


A montagem do cicruito ficou como na imagem abaixo:
![Conexão Pinos](https://github.com/Microcontroladores-2020/Santos-RFID/blob/master/imagens/circuito.JPEG)
 
## Diagrama de Blocos

O firmware funciona seguindo a lógica do diagrama de blocos abaixo, que faz o acendimento de 2 leds dependendo do tipo de sinal recebido do RC522, como liberação da entrada ou não.

![Diagrama de Blocos](https://github.com/Microcontroladores-2020/Santos-RFID/blob/master/imagens/Diagrama Leitor RFID.png)