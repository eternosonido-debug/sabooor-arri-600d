# Sabooor ARRI — Canon EOS Rebel T3i / 600D

[Português (Brasil)](#português-brasil) · [English](#english) · [5D Mark III](https://github.com/eternosonido-debug/sabooor-arri-5d)

## Português (Brasil)

Mod visual para **Canon EOS Rebel T3i / EOS 600D, firmware Canon 1.0.2**, baseado no Magic Lantern. A câmera T3i e a 600D correspondem ao mesmo alvo deste projeto.

O Sabooor ARRI traz menu inspirado no mapa ALEXA 35, HOME e monitor com moldura preta e REC/STBY, preservando os recursos originais do ML e ligando os itens disponíveis a controles reais. Funções sem equivalente permanecem N/A. Projeto independente, sem afiliação à Canon, ARRI ou Fujifilm.

### Recursos

- Menu, HOME, dados de exposição e cartão ativo; INFO acessa a apresentação original.
- Resoluções Canon: 1920x1080, 1280x720 e 640x480. Seletores NTSC sem opções 25/50.
- Project Rate: 23.976, 24, 29.97, 30 e 59.94. **24 e 30 são atalhos arredondados para 23,976 e 29,97**, não taxas exatas diferentes.
- 59.94 muda para 1280x720 e mostra popup depois de confirmar a alteração. As demais escolhas adaptam a resolução quando necessário. É preciso selecionar NTSC no menu Canon; o mod não troca o padrão automaticamente.
- Guias 16:9, 2,35:1, 1:1 e 9:16; prévia anamórfica e zoom nativo com bloqueio durante gravação.
- Looks Fuji Provia 100F, Velvia 50 e Superia X400 com intensidade: emulações criativas somente na prévia LCD. **Não alteram o H.264 nem aplicam LUT ao HDMI.**
- Fontes livres FiraGO sob SIL OFL. As fontes DIN do experimento pessoal não são redistribuídas.

### Estado e download

[Pacote experimental 600D.102](dist/sabooor-arri-600D.102-experimental.zip) · [SHA256](dist/SHA256SUMS.txt) · [Instalação / Installation](docs/INSTALACAO.md).

Este pacote comunitário usa o código compartilhado 2f52a71, derivado da versão 600D 871ab1f. Compilação ARM e testes de código no computador passaram; o limite reservado da 600D apresentou margem de 1.536 bytes. **Este build com fontes livres não foi testado fisicamente pelo assistente.** Relatos anteriores do protótipo pessoal não validam automaticamente este pacote.

Destina-se a colaboradores com Magic Lantern já funcionando no firmware exato. O ZIP não contém instalador FIR e não altera bootflags. Não copie em outra câmera ou firmware. Faça backup do core, símbolo, fontes e configurações; não formate o cartão.

### Código e compilação

O patch inclui o mod e seus recursos. O preparador reconstrói a árvore GPL completa a partir de upstream fixado e confere o checksum do patch.

```sh
python3 prepare.py source
export ARM_BINPATH=/caminho/arm-gnu-toolchain/bin
sh source/tools/build-sabooor-community.sh 600D.102 -j4
```

Requer Git, Make, Python 3 e toolchain ARM bare-metal; o build local usou Arm GNU 13.2.Rel1. Os testes de renderização precisam de Pillow e de um compilador C do computador. Veja docs/VALIDACAO.md. GPL-2.0-or-later, FiraGO SIL OFL e emulações MIT; avisos em LICENSE e LICENSES.

## English

A Magic Lantern visual mod for the **Canon EOS Rebel T3i / EOS 600D running Canon firmware 1.0.2**. T3i and 600D identify the same target in this project.

Sabooor ARRI adds an ALEXA 35 menu-map-inspired interface, HOME screen and black monitoring frame with REC/STBY. Original ML features remain available; supported items use real camera controls and unavailable functions remain N/A. This independent project is not affiliated with Canon, ARRI or Fujifilm.

### Features

- Menu, HOME, exposure and active-card information; INFO opens the original ML presentation.
- Native 1920x1080, 1280x720 and 640x480 resolutions; NTSC selectors exclude 25/50.
- Project Rate labels: 23.976, 24, 29.97, 30 and 59.94. **24/30 are rounded aliases for native 23.976/29.97, not distinct exact frame rates.**
- Selecting 59.94 switches to 1280x720 and displays a popup after Canon confirms the change. Other choices adapt resolution when required. Select NTSC in Canon's menu first; Sabooor never changes the video standard automatically.
- 16:9, 2.35:1, 1:1 and 9:16 guides, anamorphic preview and native zoom guarded during recording.
- Fuji Provia 100F, Velvia 50 and Superia X400 creative emulations with intensity control: **LCD preview only; recorded H.264 and HDMI do not receive the LUT.** These are not official Fujifilm simulations.
- Redistributable FiraGO SIL OFL fonts. Proprietary DIN files from the personal prototype are excluded.

### Status and download

[Experimental 600D.102 package](dist/sabooor-arri-600D.102-experimental.zip) · [SHA256](dist/SHA256SUMS.txt) · [Installation](docs/INSTALACAO.md).

The community package uses shared source 2f52a71, based on the 600D version 871ab1f. ARM compilation and host code tests passed; the 600D reserved-memory check reported a 1,536-byte margin. **The assistant has not tested this free-font build on physical hardware.** Previous personal-prototype reports do not validate this package.

For contributors with working ML on the exact supported firmware. The ZIP has no FIR installer and does not change bootflags. Back up the existing core, symbols, fonts and settings. Do not use on another model or firmware; do not format the card.

### Source and build

The versioned patch includes the mod and assets. prepare.py verifies its checksum and reconstructs the complete GPL source from the pinned upstream revision.

```sh
python3 prepare.py source
export ARM_BINPATH=/path/to/arm-gnu-toolchain/bin
sh source/tools/build-sabooor-community.sh 600D.102 -j4
```

Requires Git, Make, Python 3 and an ARM bare-metal toolchain; local builds used Arm GNU 13.2.Rel1. Rendering tests also require Pillow and a host C compiler. Source: GPL-2.0-or-later; FiraGO: SIL OFL; film emulation generator: MIT. Notices are included in LICENSE and LICENSES.
