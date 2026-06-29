<div align="center">

<img src="imagem_1.png" alt="ZATINO V2 PTH — Vista Superior da PCB" width="800"/>

# ZATINO V2 PTH


**Placa de desenvolvimento compatível com Arduino Uno, com componentes através-furo (PTH), programação USB-C via módulo FT232RL**

[![KiCad](https://img.shields.io/badge/KiCad-9.0-blue?logo=kicad&logoColor=white)](https://www.kicad.org/)
[![MCU](https://img.shields.io/badge/MCU-ATmega328P--PU-red)](https://www.microchip.com/en-us/product/atmega328p)
[![Licença](https://img.shields.io/badge/Licen%C3%A7a-Open%20Hardware-green)](https://www.oshwa.org/)
[![Versão](https://img.shields.io/badge/Vers%C3%A3o-V2-orange)](.)
[![ZAT ELECTRONIC](https://img.shields.io/badge/Feito%20por-ZAT%20Electronic-black)](.)

</div>

---

## 📋 Índice

- [ZATINO V2 PTH](#zatino-v2-pth)
  - [📋 Índice](#-índice)
  - [Visão Geral](#visão-geral)
  - [Renders 3D](#renders-3d)
  - [Diferenças em relação ao ZATINO SMD V2](#diferenças-em-relação-ao-zatino-smd-v2)
  - [Funcionalidades](#funcionalidades)
  - [Especificações Técnicas](#especificações-técnicas)
  - [Lista de Materiais](#lista-de-materiais)
  - [Arquitetura de Alimentação](#arquitetura-de-alimentação)
  - [Compatibilidade de Pinos](#compatibilidade-de-pinos)
  - [Estrutura do Repositório](#estrutura-do-repositório)
  - [Como Usar](#como-usar)
    - [Abrindo no KiCad](#abrindo-no-kicad)
    - [Programando a Placa](#programando-a-placa)
    - [Dica de Montagem](#dica-de-montagem)
  - [Sobre](#sobre)

---

## Visão Geral

**ZATINO V2 PTH** é uma placa de desenvolvimento personalizada, compatível com Arduino Uno, projetada pela **ZAT ELECTRONIC** utilizando o **KICAD 10**. Diferente da versão SMD, esta placa utiliza exclusivamente **componentes através-furo (PTH — Pin Through Hole)**, tornando-a ideal para montagem manual, prototipagem, aprendizado e laboratórios maker.

O microcontrolador principal é o clássico **ATmega328P-PU** no encapsulamento **DIP-28**, encaixado diretamente na placa. A programação é feita via **USB-C** através do módulo **FT232RL**, conectado a um conector fêmea de 6 pinos na borda da placa.

> 💡 Esta placa mantém **total compatibilidade de pinos com o Arduino Uno R3**, permitindo o uso de shields e bibliotecas existentes sem qualquer modificação.

---

## Renders 3D

<div align="center">

<img src="imagem_1.png" alt="Vista Superior" width="700"/>

*Vista superior — componentes PTH, LEDs coloridos e serigrafia*

<br/>

<img src="imagem_2.png" alt="Vista Isométrica" width="700"/>

*Vista isométrica — ATmega328P-PU DIP-28, módulo FT232RL USB-C e montagem geral*

</div>

---

## Diferenças em relação ao ZATINO SMD V2

| Característica | ZATINO V2 PTH | ZATINO SMD V2 |
|----------------|--------------|--------------|
| **Microcontrolador** | ATmega328P-PU (DIP-28) | ATmega328PB-AU (TQFP-32) |
| **Tipo de componentes** | Através-furo (PTH) | Montagem superficial (SMD) |
| **LEDs** | 5mm PTH (vermelho e azul) | SMD 1210 |
| **Resistores** | Axial 0,5W PTH | SMD 1206 |
| **Capacitores** | Eletrolítico + Disco cerâmico PTH | SMD 0805 |
| **Cristal** | PTH HC-49 | SMD HC-49/SD |
| **Montagem** | Manual / Soldagem fácil | Reflow / Soldagem SMD |
| **Público alvo** | Iniciantes, makers, laboratório | Produção, compacto, profissional |

---

## Funcionalidades

- ✅ **ATmega328P-PU** — encapsulamento DIP-28 PTH, 100% compatível com Arduino Uno
- ✅ **Programação via USB-C** pelo módulo FT232RL (conector plugável)
- ✅ **Duplo regulador de tensão** — 5V (AMS1117-5.0) e 3,3V (AMS1117-3.3)
- ✅ **Proteção contra inversão de polaridade** via diodo 1N4007 PTH na entrada de alimentação
- ✅ **Oscilador a cristal de 16 MHz** (encapsulamento PTH HC-49)
- ✅ **Pinout completo Arduino Uno R3** — conectores Digital, Analógico, Alimentação e ICSP
- ✅ **LED vermelho e LED azul** (5mm PTH) para sinalização de status
- ✅ **Botão de reset tátil** (THT 6×6×5 mm)
- ✅ **Entrada de alimentação Barrel Jack (P4)** com chave integrada
- ✅ **Todos os componentes PTH** — ideal para soldagem manual e aprendizado
- ✅ **Projetado com KICAD 10** — EDA totalmente open source
- ✅ **Logotipo Open Source Hardware** na PCB

---

## Especificações Técnicas

| Parâmetro | Valor |
|-----------|-------|
| **Microcontrolador** | ATmega328P-PU (DIP-28) |
| **Velocidade de Clock** | 16 MHz (cristal externo PTH) |
| **Tensão de Operação** | 5V |
| **Tensão de Entrada** | 7–12V (Barrel Jack P4) |
| **Saída 3,3V** | AMS1117-3.3 (até 800mA) |
| **Regulador 5V** | AMS1117-5.0 |
| **Interface USB** | USB-C via módulo FT232RL |
| **Pinos Digital I/O** | 14 (D0–D13), PWM em D3, D5, D6, D9, D10, D11 |
| **Entradas Analógicas** | 6 (A0–A5) |
| **Memória Flash** | 32 KB (ATmega328P) |
| **SRAM** | 2 KB |
| **EEPROM** | 1 KB |
| **Tipo de Montagem** | PTH — Através-furo |
| **Ferramenta de Projeto** | KICAD 10.0 |
| **Versão da PCB** | V2 — 2025 |
| **Fator de Forma** | Compatível com Arduino Uno R3 |

---

## Lista de Materiais

| Ref | Componente | Valor / Parte | Encapsulamento |
|-----|-----------|--------------|----------------|
| MICROCONTROLADOR1 | Microcontrolador | ATmega328P-PU | DIP-28 PTH |
| REGULADOR_5V1 | Regulador de Tensão 5V | AMS1117-5.0 | SOT-223 |
| REGULADOR_3V3 | Regulador de Tensão 3,3V | AMS1117-3.3 | SOT-223 |
| 16MHZ1 | Oscilador a Cristal | 16 MHz | HC-49 PTH |
| BARRA_DE_PINO2 | Conector FTDI | FT232RL USB-C | Fêmea 6 pinos 2,54mm |
| A2 | Referência de Pinout | Arduino Uno R3 | — |
| D1 | Diodo Retificador | 1N4007 | PTH Axial |
| L1 | LED de Status | LED 5mm Vermelho | PTH 5mm |
| L2 | LED de Status | LED 5mm Azul | PTH 5mm |
| R1 | Resistor de LED | 470Ω | Axial 0,5W PTH |
| R2 | Resistor de LED | 220Ω | Axial 0,5W PTH |
| R3 | Resistor de Pull-up | 10KΩ | Axial 0,5W PTH |
| C1, C2, C3 | Capacitores Eletrolíticos | 10µF / 50V | PTH 5×11mm |
| C4, C5 | Capacitores de Cristal | 22pF | Disco Cerâmico PTH |
| C6, C7 | Capacitores de Bypass | 100nF | Disco Cerâmico PTH |
| CONECTOR1 | Conector de Alimentação DC | Barrel Jack P4 | PTH Horizontal |
| BARRA_DE_PINO1 | Conector Auxiliar | 2 terminais | PTH 2,54mm |
| TACTIL_SWITCH1 | Botão de Reset | 6×6×5mm | THT Tátil |
| TP1 | Ponto de Teste | — | PTH |

---

## Arquitetura de Alimentação

```
VIN (Barrel Jack P4)
        │
    [1N4007]  ← Proteção contra inversão de polaridade
        │
   ┌────┴────┐
   │         │
[AMS1117-5.0]  [AMS1117-3.3]
   │         │
  +5V       +3,3V
   │
[ATmega328P-PU DIP-28]
   │
[FT232RL USB-C] ← UART TX/RX + DTR (auto-reset)
```

A placa suporta duas fontes de alimentação:
- **Barrel Jack (P4)** — entrada de 7 a 12V DC, regulada para 5V e 3,3V internamente
- **USB-C via módulo FT232RL** — 5V direto do USB, alimentando o rail VCC quando conectado

---

## Compatibilidade de Pinos

A placa expõe o **pinout completo do Arduino Uno R3**:

| Conector | Pinos |
|----------|-------|
| Digital (PWM) | D0–D13, com PWM em ~3, ~5, ~6, ~9, ~10, ~11 |
| Entradas Analógicas | A0–A5 |
| Alimentação | VIN, 5V, 3V3, GND, AREF, IOREF, RESET |
| ICSP | MISO, MOSI, SCK, RESET, VCC, GND |
| UART (FT232RL) | TX, RX (via conector BARRA_DE_PINO2) |
| I2C | SDA (A4), SCL (A5) |

---

## Estrutura do Repositório

```
ZATINO_PTH_V2/
├── ZATINO_PTH_V2.kicad_pro       # Arquivo de projeto KiCad
├── ZATINO_PTH_V2.kicad_sch       # Esquemático (KICAD 10)
├── ZATINO_PTH_V2.kicad_pcb       # Layout da PCB (KICAD 10)
├── ZATINO_PTH_V2.kicad_prl       # Configurações locais do projeto
├── packages3D/                   # Modelos 3D arquivados (STEP / WRL)
│   ├── atmega328.STEP
│   ├── AMS1117_3V3_axisY.step
│   ├── AMS1117_5V_axisY.step
│   ├── Waveshare_FT232RL_USB-C.step
│   ├── Cristal 16MHz.STEP
│   ├── LED 5mm Red.step
│   ├── LED 5mm Blue.step
│   ├── Diodo 1N4007.STEP
│   └── ...
├── fp-info-cache                 # Cache de footprints
├── fabrication-toolkit-options.json
├── imagem_1.png                  # Render superior da PCB
├── imagem_2.png                  # Render isométrico da PCB
└── README.md
```

---

## Como Usar

### Abrindo no KiCad

1. Instale o **KICAD 10.0** ou superior
2. Clone este repositório:
   ```bash
   git clone https://github.com/seu-usuario/ZATINO_PTH_V2.git
   ```
3. Abra o arquivo `ZATINO_PTH_V2.kicad_pro` no KiCad

### Programando a Placa

1. Encaixe o **módulo FT232RL USB-C** no conector de 6 pinos (`BARRA_DE_PINO2`)
2. Conecte via USB-C ao computador
3. Abra o **Arduino IDE** ou **PlatformIO**
4. Selecione a placa: **Arduino Uno**
5. Selecione a porta COM correta e faça o upload do sketch

### Dica de Montagem

> 🔧 Por ser totalmente PTH, a placa pode ser soldada com ferro de solda convencional. Recomenda-se seguir a ordem: componentes baixos primeiro (resistores, diodo, cristal), depois capacitores, reguladores, soquete DIP-28 e por último os conectores e LEDs.

---

## Sobre

<div align="center">

Projetado por **ZAT ELECTRONIC**

*ZATINO V2 PTH — 2025*

[![KiCad](https://img.shields.io/badge/Projetado%20com-KiCad-blue)](https://www.kicad.org/)
[![Open Source Hardware](https://img.shields.io/badge/Open%20Source-Hardware-brightgreen)](https://www.oshwa.org/)

</div>