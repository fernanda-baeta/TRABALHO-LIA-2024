# Resultados Finais
## Montagem Física:

A montagem física do projeto é simples e eficaz. O sensor DHT11 (ou DHT22) está conectado corretamente aos pinos do Arduino, e o display LCD está funcionando, mostrando as leituras de temperatura e umidade em tempo real.
O circuito utiliza componentes básicos como jumpers e resistores, e pode ser montado facilmente em uma placa de ensaio (breadboard).

## Leitura dos Dados:

O Arduino está recebendo os dados do sensor de temperatura e umidade de maneira precisa, com uma atualização frequente (intervalos de 2 segundos).
Exemplo de leituras no display:
Temperatura: 25°C
Umidade: 60%
O display LCD exibe as informações de forma clara, permitindo uma visualização rápida e direta.

## Funcionamento do Código:

O código desenvolvido lê as informações do sensor DHT e as exibe no display. Ele funciona corretamente sem erros ou atrasos significativos.
O código pode ser facilmente ajustado para modificar a frequência das leituras ou adicionar funcionalidades extras, como alertas.
Consistência das Leituras:

O sensor DHT11, apesar de ser uma opção básica, apresenta leituras estáveis e suficientemente precisas para um projeto doméstico ou educacional.
O uso do DHT22 aumentaria a precisão e a faixa de medição, se necessário.

## Opções de Expansão:

Embora o sistema básico funcione bem, ele pode ser expandido com conectividade Wi-Fi, permitindo o envio dos dados para um serviço de nuvem como o ThingSpeak para monitoramento remoto.
Outra possível adição seria a implementação de alarmes visuais ou sonoros quando os limites de temperatura ou umidade são ultrapassados.

# Análise Geral do Projeto

## Facilidade de Implementação:

O projeto foi fácil de implementar devido à simplicidade dos componentes e à vasta disponibilidade de bibliotecas prontas para o Arduino. Isso torna o projeto uma excelente escolha para iniciantes.
A curva de aprendizado foi suave, com foco em entender a integração básica de sensores e displays com o Arduino.

## Custo-Benefício:

O projeto utiliza componentes acessíveis como o DHT11 (ou DHT22), o Arduino, e um display LCD. O custo total é baixo, o que torna o projeto viável para estudantes e hobbystas.
O sensor DHT11 é barato, mas se for necessário mais precisão ou uma faixa de medição maior, o DHT22 pode ser utilizado como uma atualização de baixo custo.

## Eficiência e Precisão:

Para uso doméstico ou em pequenos ambientes, o sistema fornece leituras com precisão suficiente. No entanto, a precisão do DHT11 tem limites em comparação com sensores mais caros. O DHT22 é uma opção melhor se for necessária maior precisão.
A atualização constante dos dados no display permite um monitoramento em tempo real, o que é útil para manter o controle do ambiente monitorado.

## Expansibilidade:

Uma das grandes vantagens deste projeto é sua fácil expansibilidade. Você pode adicionar:
Módulo Wi-Fi (ESP8266) para enviar dados para a nuvem.
Alarmes de segurança para alertar quando a temperatura ou a umidade atingirem certos limites.
Integração com outros sistemas, como automação residencial ou controle de ventilação, com base nas leituras do sensor.
Estas expansões aumentam a complexidade, mas oferecem grande valor em termos de funcionalidade.

## Aplicações Práticas:

O projeto tem várias aplicações no mundo real, como:
Monitoramento de temperatura e umidade em estufas ou salas de servidores.
Controle de ambiente em residências ou escritórios.
Sistema de monitoramento de ambientes com sensibilidade a condições climáticas, como adegas de vinhos ou depósitos de alimentos.

