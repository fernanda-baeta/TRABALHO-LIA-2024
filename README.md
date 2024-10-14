# TRABALHO-LIA-2024
## Monitoramento de Temperatura e Umidade
O objetivo desse projeto é fazer um sistema que monitora e exibe em tempo real a temperatura e a umidade de um ambiente. Pode enviar alertas quando os valores ultrapassarem determinados limites.
### Componentes Necessários:
   - Arduino Uno 
   - Sensor de Temperatura e Umidade DHT11 ou DHT22
   - Display LCD 16x2 ou OLED
   - Resistores (casp seja necessário)
   - Jumpers e uma placa de ensaio (breadboard)
   - Fonte de alimentação (ou cabo USB para o Arduino)

### Funcionamento do Projeto

O projeto utiliza um sensor DHT11 (ou DHT22) para capturar os valores de temperatura e umidade do ambiente. Esses dados são enviados para o Arduino, que processa as informações e as exibe em um display LCD (ou OLED). A atualização dos dados ocorre em intervalos regulares (por exemplo, a cada 2 segundos), permitindo que o usuário acompanhe as mudanças em tempo real. O sistema é alimentado via USB (ou uma fonte externa) e funciona de maneira contínua enquanto está energizado.

### *Esquema de Conexão*

O esquema de conexão depende dos componentes escolhidos. Aqui está uma descrição para montar o circuito:

1. *Conectando o Sensor DHT11/DHT22:*
   - *VCC* (pino 1 do sensor) -> *5V* do Arduino.
   - *Data* (pino 2 do sensor) -> Pino digital 2 do Arduino (com um resistor de pull-up de 10kΩ entre este pino e o 5V).
   - *GND* (pino 4 do sensor) -> *GND* do Arduino.

2. *Conectando o Display LCD (com módulo I2C):*
   - *VCC* (pino do módulo I2C) -> *5V* do Arduino.
   - *GND* (pino do módulo I2C) -> *GND* do Arduino.
   - *SDA* (pino do módulo I2C) -> Pino *A4* do Arduino.
   - *SCL* (pino do módulo I2C) -> Pino *A5* do Arduino.

### Código do Projeto

Abaixo está o código para o Arduino que lê os dados do sensor DHT e os exibe no display LCD. Ele utiliza bibliotecas específicas para facilitar a comunicação com os componentes:

#### *Código Arduino:*

cpp
#include <DHT.h>
#include <Wire.h>
#include <LiquidCrystal_I2C.h>

// Definindo o pino do sensor e o tipo (DHT11 ou DHT22)
#define DHTPIN 2
#define DHTTYPE DHT11 // Altere para DHT22 se estiver usando esse sensor

// Criando objeto para o sensor DHT
DHT dht(DHTPIN, DHTTYPE);

// Configurando o display LCD (endereço padrão: 0x27 e tamanho: 16x2)
LiquidCrystal_I2C lcd(0x27, 16, 2);

void setup() {
  // Inicializa o display LCD e o sensor DHT
  lcd.begin();
  lcd.backlight();
  dht.begin();
  
  // Mensagem inicial
  lcd.setCursor(0, 0);
  lcd.print("Monitoramento");
  lcd.setCursor(0, 1);
  lcd.print("Iniciando...");
  delay(2000); // Pausa de 2 segundos
}

void loop() {
  // Lendo a umidade e temperatura
  float humidity = dht.readHumidity();
  float temperature = dht.readTemperature();
  
  // Verificando se as leituras são válidas
  if (isnan(humidity) || isnan(temperature)) {
    lcd.setCursor(0, 0);
    lcd.print("Erro ao ler ");
    lcd.setCursor(0, 1);
    lcd.print("sensor DHT!");
  } else {
    // Exibindo a temperatura e umidade no display
    lcd.clear();
    lcd.setCursor(0, 0);
    lcd.print("Temp: ");
    lcd.print(temperature);
    lcd.print(" C");
    
    lcd.setCursor(0, 1);
    lcd.print("Umid: ");
    lcd.print(humidity);
    lcd.print(" %");
  }
  
  // Pausa antes da próxima leitura
  delay(2000);
}

### Conclusão

Com o código e o circuito montados, o sistema está pronto para monitorar a temperatura e umidade do ambiente em tempo real. Se você desejar expandir o projeto, é possível adicionar conectividade Wi-Fi com o módulo ESP8266 para enviar os dados para a internet, ou até criar um sistema de alerta visual/sonoro para avisar sobre mudanças críticas nas condições do ambiente.

