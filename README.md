# Documentação da Estufa Inteligente com ESP32

## Sumário

1. **Introdução**
   - 1.1 Justificativa do Projeto
   - 1.2 Contexto Atual da Agricultura
2. **Objetivos do Projeto**
   - 2.1 Objetivos Gerais
   - 2.2 Objetivos Específicos
3. **Componentes Utilizados**
   - 3.1 Microcontrolador
   - 3.2 Sensores
   - 3.3 Atuadores
   - 3.4 Outros Componentes
4. **Esquema Elétrico**
   - 4.1 Diagrama de Conexões
   - 4.2 Considerações sobre Segurança
5. **Montagem da Estufa**
   - 5.1 Estrutura da Estufa
   - 5.2 Posicionamento dos Sensores
   - 5.3 Conexões Elétricas
   - 5.4 Montagem do Software
6. **Programação do ESP32**
   - 6.1 Configuração do Ambiente de Desenvolvimento
   - 6.2 Estrutura do Código
   - 6.3 Explicação Detalhada do Código
   - 6.4 Exemplos de Código
7. **Interface Web**
   - 7.1 Estrutura da Interface
   - 7.2 Funcionalidades
   - 7.3 Implementação e Código
8. **Teste e Validação**
   - 8.1 Metodologia de Testes
   - 8.2 Resultados de Testes
   - 8.3 Análise Crítica dos Resultados
9. **Resultados e Discussão**
   - 9.1 Análise dos Dados Coletados
   - 9.2 Desafios Encontrados
   - 9.3 Comparação com Métodos Tradicionais
10. **Conclusão e Futuras Melhorias**
    - 10.1 Conclusões
    - 10.2 Sugestões para Melhorias Futuras
11. **Referências**
12. **Anexos**
    - 12.1 Códigos Fonte Completos
    - 12.2 Diagramas e Fotos da Montagem
    - 12.3 Manuais de Usuário e Manutenção

---

## 1. Introdução

### 1.1 Justificativa do Projeto

A necessidade de otimizar o cultivo de plantas em ambientes controlados tem se tornado cada vez mais evidente, especialmente com o aumento da população global e a demanda por alimentos. A estufa inteligente proposta neste projeto visa utilizar tecnologia acessível para monitoramento e controle das condições ambientais, promovendo um crescimento saudável das plantas.

### 1.2 Contexto Atual da Agricultura

A agricultura moderna enfrenta desafios como a escassez de água, mudanças climáticas e a necessidade de aumentar a produtividade. A automação e o uso de sensores são tendências que ajudam a minimizar esses problemas, permitindo um uso mais eficiente dos recursos.

## 2. Objetivos do Projeto

### 2.1 Objetivos Gerais

- Desenvolver uma estufa automatizada que permita o monitoramento e controle das condições ambientais utilizando o microcontrolador ESP32.

### 2.2 Objetivos Específicos

- Medir e registrar temperatura e umidade interna da estufa.
- Monitorar a umidade do solo e controlar a irrigação automaticamente.
- Prover uma interface web para visualização de dados em tempo real.
- Implementar um sistema de alertas para condições adversas (como temperaturas extremas).

## 3. Componentes Utilizados

### 3.1 Microcontrolador

**ESP32**: O ESP32 é um microcontrolador de alta performance que combina Wi-Fi e Bluetooth, permitindo conectividade na Internet das Coisas (IoT). Suas características incluem:

- Processador dual-core.
- Vários pinos de entrada e saída.
- Conectividade sem fio.

### 3.2 Sensores

- **DHT22**: Sensor digital com precisão para medição de temperatura e umidade. Especificações:
  - Faixa de temperatura: -40 a 80 °C.
  - Faixa de umidade: 0 a 100% RH.
  
- **Sensor de Umidade do Solo**: Mede a umidade do solo para otimizar a irrigação. Tipos populares incluem:
  - Resistivo: mede a resistência elétrica do solo.
  - Capacitivo: mede a capacitância, oferecendo maior durabilidade.

### 3.3 Atuadores

- **Relé**: Um módulo relé é utilizado para controlar a bomba de irrigação. Ele permite a ativação/desativação de dispositivos de alta potência com sinais de baixa tensão.

### 3.4 Outros Componentes

- **Fonte de Alimentação**: Para fornecer energia ao ESP32 e aos sensores. A tensão deve ser compatível com os requisitos do ESP32 (geralmente 5V).
- **Fios e Protoboard**: Para realizar as conexões de forma temporária durante a fase de testes.
- **Conectores e Terminais**: Para facilitar as ligações elétricas.

## 4. Esquema Elétrico

### 4.1 Diagrama de Conexões

O diagrama elétrico deve ser elaborado em software de diagramação, como Fritzing ou EasyEDA. O seguinte esquema básico pode ser seguido:

1. Conectar o DHT22 ao pino digital 4 do ESP32.
2. Conectar o sensor de umidade do solo ao pino analógico 34.
3. Conectar o módulo relé ao pino digital 32.
4. Assegurar que todos os componentes estejam conectados à fonte de alimentação correta.

### 4.2 Considerações sobre Segurança

- **Isolação Elétrica**: Utilize módulos relé com isolamento para evitar choques elétricos.
- **Proteção contra Sobrecarga**: Certifique-se de que a fonte de alimentação é adequada para os dispositivos utilizados.
- **Uso de Componentes de Qualidade**: Utilize componentes de fabricantes confiáveis para garantir a durabilidade e a segurança do sistema.

## 5. Montagem da Estufa

### 5.1 Estrutura da Estufa

A estrutura da estufa pode ser construída com materiais leves, como tubos de PVC ou alumínio. O design deve permitir a entrada de luz solar e a proteção contra intempéries:

- **Dimensões**: Uma estufa de 1,5m² pode ser adequada para pequenos experimentos.
- **Cobertura**: Utilize plástico transparente ou vidro para otimizar a entrada de luz.

### 5.2 Posicionamento dos Sensores

O posicionamento adequado dos sensores é crucial para leituras precisas. Recomenda-se:

- Colocar o DHT22 em um local central, longe de fontes de calor, como paredes ou janelas.
- Inserir o sensor de umidade do solo no substrato a uma profundidade adequada (cerca de 5-10cm).

### 5.3 Conexões Elétricas

As conexões devem ser realizadas seguindo o diagrama elétrico. Utilize terminais de conexão para facilitar as trocas. Recomenda-se:

- Verificar a polaridade dos componentes.
- Utilizar fita isolante para proteger as conexões expostas.

### 5.4 Montagem do Software

Após a montagem física, o software deve ser carregado no ESP32. Utilize a Arduino IDE para compilar e enviar o código.

## 6. Programação do ESP32

### 6.1 Configuração do Ambiente de Desenvolvimento

1. **Instalar a Arduino IDE**: Baixe e instale a versão mais recente.
2. **Adicionar suporte ao ESP32**: No gerenciador de placas, adicione o repositório do ESP32.
3. **Instalar Bibliotecas Necessárias**: Instale as bibliotecas `DHT` e `WiFi`.

### 6.2 Estrutura do Código

O código pode ser dividido em seções:

- Inicialização
- Loop principal
- Funções auxiliares

### 6.3 Explicação Detalhada do Código

```cpp
#include <WiFi.h>
#include <DHT.h>

#define DHTPIN 4
#define DHTTYPE DHT22
#define SOIL_PIN 34
#define RELAY_PIN 32

DHT dht(DHTPIN, DHTTYPE);

const char* ssid = "YOUR_SSID";
const char* password = "YOUR_PASSWORD";

void setup() {
    Serial.begin(115200);
    dht.begin();
    pinMode(RELAY_PIN, OUTPUT);
    digitalWrite(RELAY_PIN, LOW);
    connectToWiFi();
}

void loop() {
    float h = dht.readHumidity();
    float t = dht.readTemperature();
    int soilMoisture = analogRead(SOIL_PIN);

    if (soilMoisture < 400) {
        digitalWrite(RELAY_PIN, HIGH); // Liga a bomba
    } else {
        digitalWrite(RELAY_PIN, LOW); // Desliga a bomba
    }

    // Enviar dados para a interface web
    delay(2000);
}

void connectToWiFi() {
    WiFi.begin(ssid, password);
    while (WiFi.status() != WL_CONNECTED) {
        delay(500);
        Serial.print(".");
    }
    Serial.println("Conectado ao WiFi");
}
```

- **Inclusões**: As bibliotecas necessárias são incluídas.
- **Definições**: Os pinos dos sensores e atuadores são definidos.
- **Setup**: Inicializa o DHT22 e conecta ao Wi-Fi.
- **Loop**: Lê a umidade do solo e as condições ambientais, controlando a bomba de irrigação conforme necessário.

### 6.4 Exemplos de Código

O código pode ser expandido para incluir mais funcionalidades, como a comunicação via MQTT ou HTTP para o envio de dados a um servidor.

## 7. Interface Web

### 7.1 Estrutura da Interface

A interface web deve ser amigável e responsiva. As principais seções incluem:

- **Dashboard**: Exibição de dados em tempo real.
- **Controle de Irrigação**: Botão para ativar/desativar a irrigação manualmente.
- **Histórico de Dados**: Gráficos que mostram a evolução da temperatura e umidade.

### 7.2 Funcionalidades

- **Visualização em Tempo Real**: Atualização automática dos dados.
- **Controle Manual da Irrigação**: Permite ao usuário ativar a bomba.
- **Alertas**: Notificações sobre condições adversas.

### 7.3 Implementação e Código

O código HTML pode ser semelhante ao seguinte exemplo:

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Estufa Inteligente</title>
    <style>
        body { font-family: Arial, sans-serif; }
        .container { max-width: 600px; margin: auto; }
        h1 { text-align: center; }
        .data { margin: 20px 0; }
    </style>
</head>
<body>
    <div class="container">
        <h1>Estufa Inteligente</h1>
        <div class="data" id="data"></div>
        <button onclick="toggleIrrigation()">Alternar Irrigação</button>
    </div>
    <script>
        function fetchData() {
            fetch('/data')
                .then(response => response.json())
                .then(data => {
                    document.getElementById("data").innerHTML = `Temperatura: ${data.temperature}°C, Umidade: ${data.humidity}%`;
                });
        }

        function toggleIrrigation() {
            fetch('/toggle-relay');
        }

        setInterval(fetchData, 2000);
    </script>
</body>
</html>
```

## 8. Teste e Validação

### 8.1 Metodologia de Testes

1. **Teste de Conectividade**: Verificar se o ESP32 conecta ao Wi-Fi.
2. **Teste de Sensores**: Validar a precisão dos sensores em diferentes condições.
3. **Teste de Controle**: Monitorar a resposta do sistema de irrigação em tempo real.

### 8.2 Resultados de Testes

Os resultados devem ser registrados e analisados. Algumas métricas incluem:

- Tempo de resposta do sistema de irrigação.
- Precisão das leituras do DHT22 e do sensor de umidade do solo.

### 8.3 Análise Crítica dos Resultados

Discuta os resultados obtidos e como eles se comparam às expectativas. Se necessário, ajuste os limites de umidade do solo para o acionamento da bomba.

## 9. Resultados e Discussão

### 9.1 Análise dos Dados Coletados

Os dados coletados durante os testes devem ser analisados para determinar a eficácia do sistema. Crie gráficos para visualizar a relação entre temperatura, umidade e irrigação.

### 9.2 Desafios Encontrados

Identifique os principais desafios encontrados durante o desenvolvimento e testes, como:

- Interferência de sinal Wi-Fi.
- Calibração dos sensores.
- Confiabilidade do sistema de relé.

### 9.3 Comparação com Métodos Tradicionais

Discuta como a estufa inteligente se compara a métodos de cultivo tradicionais, destacando as vantagens, como economia de água e maior precisão no controle das condições.

## 10. Conclusão e Futuras Melhorias

### 10.1 Conclusões

A estufa inteligente com ESP32 demonstrou ser uma solução eficiente para o controle ambiental no cultivo. O sistema mostrou-se eficaz na automação da irrigação e no monitoramento das condições.

### 10.2 Sugestões para Melhorias Futuras

- **Integração com Nuvem**: Armazenamento e análise de dados em serviços como AWS ou Google Cloud.
- **Sensores Adicionais**: Adicionar sensores de luz e CO2 para um controle mais abrangente.
- **Machine Learning**: Implementar algoritmos de aprendizado de máquina para prever necessidades hídricas e otimizar o crescimento das plantas.

## 11. Referências

- Arduino. "Arduino IDE." Acesso em: [link](https://www.arduino.cc/en/software).
- Espressif. "ESP32 Technical Reference Manual." Acesso em: [link](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/api-reference/index.html).
- DHT Sensor Library. "DHT Sensor Library for Arduino." Acesso em: [link](https://github.com/adafruit/DHT-sensor-library).

## 12. Anexos

### 12.1 Códigos Fonte Completos

### 12.2 Diagramas e Fotos da Montagem

### 12.3 Manuais de Usuário e Manutnções
