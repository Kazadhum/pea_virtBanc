# pea_virtBanc
Projeto Bancada Virtual

## Feedback Apresentação M2

- Definir melhor a arquitetura do projeto
- Internet é importante para o projeto, pois ThingsBoard/MariaDB/etc são serviços IP
- Se Node-RED/sql-lite não funcionar no IoT2040, pode funcionar numa máquina à parte numa fase prévia
- Numa fase inicial, é indiferente ter a BD no IoT ou no PC
- Incompatibilidade MariaDB?
- Encontrar soluções alternativas caso esta não seja possível
- Dashboard do Node-RED é suficiente para o projeto pedido
- Bases de dados podem não ser necessárias de todo
- Discos flash são muito limitados para trabalhar com bases de dados
- Repensar o armazenamento de dados

## Feedback Reunião 20/04

- Novo Risco: IOT não foi feito para processamento de dados; pode fraquejar nesta parte
  - Solução: Se necessário, passar parte do programa para um PC a correr o Node-RED; passa-se a usar o IOT apenas como um Gateway e faz-se a recolha e comunicação dos dados por parte do IOT com recurso a programas C/Python. Preferencialmente não fazer isto, pois vai contra o objetivo do projeto de ter um dispositivo "plug-and-play" 
. No entanto, devemos fazer o programa de forma modular de forma a facilitar este tipo de alterações.
- Recebemos:
  -  Sensor de pressão IFM PT5404
    -  Mede entre 0 e 10 bar, e aguenta um máximo de 25 bar
  -  Acelerómetro
    -  Alimentado em 7,2-10,8 V
  -  Dissipador de Temperatura
  -  Módulo Wi-Fi para a fase de desenvolvimento
-  Ver se os pinos de comunicação SPI estão disponíveis por causa da carta de ligações
-  Adaptador sensor de pressão
-  Ler datasheet do sensor de vibração para ver como fazer ligações
-  Sensor de temperatura (ver com prof Pedro)
-  Boards e calha para ligações bem feitas
-  Medir o tube pneumático do LEICA
-  No ficheiro *output* do programa precisamos dos campos:
  -  Timestamp
  -  Identificação do sensor
  -  Valor medido
-  O formato .csv é bom para importar para Excel, mas não é o mais indicado para este projeto, porque os sensores precisam cada um de campos diferentes (csv são tabelas estruturadas e cada entrada na tabela tem de ter os mesmos campos que as outras, que neste caso resulta em desperdícios de memória)
-  Investigar os formatos .json e .yaml para processamento
-  Node-RED tem um node para leitura de .yaml
-  Mais tarde, podemos investigar a implementação de bases de dados não-SQL
-  Podemos integrar o sensor de distância via RS232 (maior resolução)
-  Integrar suporte para medidores de consumo
-  Display da temperatura do IOT na Dashboard
-  Numa fase inicial, fazer a configuração dos sensores via um ficheiro de texto carregado para o Node-RED

## Feedback Apresentação M3

- Marcar uma reunião com o prof e com o David
- Explorar soluções para o tamanho do ficheiro JSON
  - Arredondar valores da pressão, abreviar palavras
- Pré-alarmes

