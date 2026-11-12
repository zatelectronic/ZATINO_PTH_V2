# ZATINO PTH V2 — Revisão R01 (organização) — 2026-11-11
Zat Electronic · KiCad 10.0

## O que mudou
- Esquema plano (A4) -> capa A2 + 3 folhas: 02 MCU (A3), 03 ALIMENTACAO (A4), 04 CONEXOES (A4).
- Projeto renomeado sem espaços: ZATINO_PTH_V2.kicad_pro / .kicad_sch / .kicad_pcb.
- Reanotação (todo o esquema, ordem Y, redefinir, 1º livre após 0):
  MICROCONTROLADOR1->U1 · REGULADOR_5V1->U2 · REGULADOR_3V3->U3 · 16MHZ1->Y1 · TACTIL_SWITCH1->SW1
  BARRA_DE_PINO1->J1 (AREF) · CONECTOR1->J2 (jack) · BARRA_DE_PINO2->J3 (FTDI) · A2->A1 (headers UNO)
  L1->LED1 · L2->LED2 · C5->C1 · C4->C2 · C7->C3 · C1->C4 · C2->C5 · C3->C6 · C6->C7 · R3->R1 · R1->R2 · R2->R3
  (C1-C3 conforme a reanotação feita no KiCad)
- Values normalizados, Descrição PT, Stock Code, Package Group.
- Símbolos = biblioteca padrão KiCad 10; A1 = ZAT_Board_Arduino:ARDUINO_UNO_R3_Headers (biblioteca global).
- No Connect: J3 pino 2 (CTS) e A1 pino P1. PWR_FLAG: GND e VIN.
- PCB: nada movido. Footprints atualizados para a biblioteca KiCad 10 (pad 1 quadrado, 3D padrão).
  J3 passou para PinSocket_1x06 (barra fêmea — mesmas posições de pad).
  Logos OSHW/WEEE atualizados e marcados "Not in schematic".
- 3D em packages3D não é mais usado (pode apagar).

## Pendências de projeto (exigem alteração de placa)
- IMPORTANTE: sem 100 nF nos pinos VCC (7) e AVCC (20) do ATmega328P.
- IMPORTANTE: +5V do módulo FTDI ligado direto ao +5V da placa, sem diodo/chave (retroalimenta o AMS1117-5.0).
- ATENÇÃO: jumper J1 (AREF->3,3 V) fechado exige analogReference(EXTERNAL).
- MELHORIA: AMS1117 em SOT-223 (únicos SMD numa placa PTH).

## Após abrir no KiCad
1. Reiniciar o KiCad (biblioteca ZAT_Board_Arduino atualizada).
2. ERC no esquema.
3. PCB: B (preencher zonas) -> F8 (Update PCB from Schematic: deve vir sem alterações) -> DRC.

## Correções após o ERC/DRC do Kenneth (2026-11-11)
- C1/C2/C3: o F8 após a reanotação religou por referência e trocou os capacitores de lugar (curtos X1/X2/AREF/GND).
  PCB refeito a partir do vínculo correto (UUID), já com a numeração da reanotação do KiCad.
- Label X1 (folha MCU) estava 0,0004 mm fora da grade -> U1 pino 9 solto. Corrigido.
- A1 (ZAT_Board_Arduino:ARDUINO_UNO_R3_Headers): removido o contorno em Edge.Cuts e o courtyard da placa inteira;
  silk e courtyard só em volta dos 4 headers + furos. IOREF como pino passivo (fim do aviso pin_to_pin).
- Texto "DC IN 7V-12V" de 0,4 para 0,8 mm. Rótulos de serigrafia com referências antigas atualizados (R1-R3, C1-C7, Y1).
- .kicad_dru: exceções só para o layout original (J2 em balanço na borda, courtyards U2xU3 e C7xR1).

## Referências na serigrafia (2026-11-11)
- Todas as referências (U1-U3, J1-J3, A1, C1-C7, R1-R3, LED1-2, D1, SW1, Y1, TP1) visíveis em F.SilkS,
  1,0 mm / traço 0,15 mm, 0° ou 90°, posicionadas fora do corpo do componente, sem tocar em
  serigrafia, pads (folga 0,25 mm), outras referências (0,2 mm) ou borda (0,4 mm).
- A1: removidos os retângulos de serigrafia dos headers (a arte da placa já desenha os headers).
- .kicad_dru: exceções para a arte da placa (blocos/knockout), J3 x contorno do módulo FTDI e J2 em balanço.

## Logos (2026-11-11)
- Os 5 logos de serigrafia (ZAT, KiCad, LEDs, DC IN e OSHW) receberam courtyard real (contorno da arte + 0,25 mm),
  sem sobrepor nenhum componente. O OSHW virou arte da placa (sem vínculo com a biblioteca Symbol).

## Sem exceções (2026-11-11)
- ERC: 3 junções de 4 vias desfeitas (VIN, +5V, TP1); A1 fora da simulação (conector sem modelo SPICE).
- DRC: .kicad_dru sem nenhuma regra de exceção. U2 -0,25 mm em Y (afasta de U3), C7 +0,15 mm em X (afasta de R1);
  J2 = ZAT_Connector:BarrelJack_Horizontal_EdgeMount (serigrafia termina na borda);
  blocos GND da arte refeitos sem tocar nos textos nem nos pads; contorno do FTDI afastado do J3; linhas sob DIGITAL/ANALOG IN encurtadas.

## 3D personalizados (2026-11-11)
- 18 componentes usam footprints ZAT_ novos (cópia exata do KiCad 10 + 3D da pasta ${ZAT_3D}): LEDs vermelho/azul,
  resistores com faixas 10K/470R/220R, capacitores 22 pF / 100 nF / 10 uF, cristal 16 MHz, 1N4007, AMS1117-5.0/3.3,
  ATmega328P-PU e J3 com o módulo FT232RL USB-C. J3 usa ZAT_Connector:Conn_01x06_Pin (filtro inclui ZAT_Connector).
