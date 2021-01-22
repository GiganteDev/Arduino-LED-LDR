## 3.1 Código

<p align="center">
  <img src="https://github.com/GiganteDev/Arduino/blob/main/.github/img-arduino-logo.png" width="120">
</p>

```cpp
int valorLDR;  //armazena o valor do sinal analógico enviado pelo LDR
float luminosidade;  //armazena o valor do sinal analógico convertido em PWM 
   
void setup(){  
    pinMode(A0, INPUT); //define o pino onde o LDR está conectado como entrada de sinal 
    pinMode(6, OUTPUT); //define o pino onde o led está conectado como saída de sinal 
}  
   
void loop(){  
    valorLDR = analogRead(A0);  //faz a leitura do LDR e armazena o valor analógico 
    luminosidade = map(valorLDR, 0, 1023, 0, 255); //converte o sinal analógico em PWM
    analogWrite(6, luminosidade); //liga o led de acordo com o valor do PWM recebido
 }
```

Em uma rápida interpretação, este código fará com que o LED receba o valor lido do LDR, estado o qual é totalmente variável de acordo com a posição.

O LDR está conectado a um pino analógico e o mesmo possui resolução de 10 bits, ou seja, 2^10(2 elevado a 10) que resulta em 1024,onde você tem uma faixa de 0 a 1023, sendo 0 o valor mínimo e 1023 o valor máximo.

O LED está conectado ao pino digital 6 e o mesmo possui PWM. A resolução do PWM do Arduino é de 8 bits, ou seja, 2^8(2 elevado a 8) que resulta em 256, onde você tem uma faixa de 0 a 255, sendo 0 o valor mínimo e 255 o valor máximo.

Neste caso, temos uma conversão, onde 0 a 1023 (analógico) terá uma proporção na faixa de 0 a 255 (digital PWM) para controlar a luminosidade do LED. A variável recebe o resultado do cálculo na função map e em seguida através da função “analogWrite” escreve no pino digital 610 qual será o valor de tensão disponível para o LED.

---

<a  href="https://github.com/GiganteDev/Arduino/"><img  src="https://img.shields.io/badge/%E2%9E%94%20-Projetos-fff"/></a>