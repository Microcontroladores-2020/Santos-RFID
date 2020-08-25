## Controle de entrada com RFID

# Motivação
A ideia do projeto de controle de acesso por RFID, controlando a abertura de um relé veio da necessidade encotrada no meu dia a dia de possibilitar a entrada de várias pessoas 
na sede da IME Júnior. Atualmente a entrada é controlada por meio de um cadeado de senha, mas por comodidade e também controle seria melhor que ocorrese um registro do momento de entrada das pessoas.
Dessa forma a entrada por meio de RFID foi escolhida por se adequar ao uso do próprio crachá do IME, podendo futuramente evoluir para um sistema com registro de tempo e um banco de dados de crachá maior.

# Escopo do Projeto 
O projeto, nessa versão, implementará a leitura do sensor RFID com a informação de liberação de entrada na tela integrada da Discovery.

# Periféricos utilizados
Para a realização do projeto foi utilizado:
1. Controlador STM32F429I;
![STM32F429I-DISCO](.....)
2. Sensor RFID-RC522:
![Sensor RFID-RC522](....)
3. Tela trouchscreen integrada do controlador.

A comunicação dos sensores foi feita por meio do protocolo de comunicação I2C, para a captura de dados do leitor RFID e envio do sinal para a tela, com a mensagem do que deveria ser escrito.

# Pinagem

A pinagem do STM32 foi feita como na imagem a seguir:
![Pinout STM32](.....)
 
E com as seguintes funcionalidades:

| Pinos         | Função         | 
| ------------- |:--------------:| 
| col 3 is      | SDA RFID       | 
| col 2 is      | SCK RFID       |  
| zebra stripes | MOSI RFID      |
|               | MISO RFID      |
|               | RQ RFID        |
|               | GND RFID       |
|               | RST RFID       |

# Diagrama de Blocos
