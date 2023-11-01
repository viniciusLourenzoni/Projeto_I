#Descrição do Código
O código é destinado a um dispositivo ESP8266, que atua como um servidor web para controlar um LED conectado ao pino D1 do dispositivo.

#Bibliotecas:

####include<Arduino.h>: Biblioteca padrão para programação em plataformas Arduino.
####include <ESP8266WiFi.h>: Permite ao ESP8266 conectar-se a uma rede Wi-Fi.
####include <ESP8266WebServer.h>: Facilita a criação de um servidor web no ESP8266.

#Variáveis Globais:
-> const char* ssid e const char* password: São as credenciais da rede Wi-Fi à qual o ESP8266 se conectará.

-> ESP8266WebServer server(80): Cria um servidor web na porta 80.

-> const int output5 = 5: Define o pino D1 como a saída onde o LED está conectado.

-> IPAddress: Configurações de IP local, gateway e subnet para o dispositivo.
Funções Web:

handleRoot(): Esta função envia uma página HTML quando alguém acessa a raiz (/) do servidor. Esta página possui botões para ligar e desligar o LED.
handleOn(): Aciona o LED (coloca o pino D1 em HIGH) e envia uma resposta de texto "LED Ligado!".
handleOff(): Desliga o LED (coloca o pino D1 em LOW) e envia uma resposta de texto "LED Desligado!".
Setup e Loop:

setup(): É a função que é executada uma vez quando o ESP8266 é inicializado.

Configura a comunicação serial.
Define o pino D1 como saída e o inicializa em estado baixo (LED desligado).
Conecta-se à rede Wi-Fi usando as credenciais fornecidas.
Exibe o endereço IP atribuído ao ESP8266 na rede.
Configura os manipuladores de URL para o servidor (raiz, ligar LED, desligar LED).
Inicia o servidor.
loop(): Esta função roda continuamente após a execução do setup().

Chama server.handleClient(), permitindo que o servidor web trate as solicitações recebidas.
#Como Usar:
Conecte um LED ao pino D1 do seu dispositivo ESP8266.
Carregue este código no seu dispositivo ESP8266 usando a IDE do Arduino.
Após carregar, o dispositivo tentará se conectar à rede Wi-Fi fornecida.
Uma vez conectado, ele exibirá seu endereço IP no monitor serial.
Você pode entrar nesse IP usando qualquer navegador web.
Uma página web será exibida com dois botões: "ON" para ligar o LED e "OFF" para desligá-lo.

---

####Alunos: Vinicius Lourenzoni, Samuel Rodrigues, João Goroncy, Daniel Brisch
