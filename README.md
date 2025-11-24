# Projeto 1 - KamazKrov
Portable RF & Pentest handheld (ESP32-S3)

Visão

Criar um dispositivo portátil, replicável e open-source para pesquisa de segurança wireless e automação — pensado para aprendizado, PoCs éticos e prototipagem profissional. O KamazKrov é um laboratório de bolso: Wi-Fi/BLE, Sub-GHz, 2.4 GHz, RFID, IR, UI por touch + microSD + bateria. Objetivo: transformar curiosidade em resultados reais (dumps, logs, demos) sem sacrificar segurança e ética.


---

Objetivos do projeto — hardware

Cérebro: ESP32-S3 DevKit (USB nativo, PSRAM recomendado).

UI: Tela TFT 3.2" ILI9341 (SPI) + touch XPT2046.

Armazenamento: microSD via SPI (logs, captures, scripts).

RF: CC1101 (sub-GHz) + NRF24L01+ PA/LNA (2.4 GHz).

RFID: RC522 (13.56 MHz) — leitura/escrita básica.

Energia: Bateria Li-Po + TP4056 com proteção.

Periféricos: RTC DS3231, buzzer/speaker, IR TX/RX, botões táteis.

Conectividade física: U.FL → SMA pigtail para antenas externas.

Depuração: CH341A (programação/escrita de flashes quando necessário).



---

Base do projeto

Inspirado em: ESP32-DIV (CiferTech), Flipper Zero, High Boy.

Filosofia: hardware modular + firmware open (C/C++ ou ESP-IDF / Arduino / Micropython) + foco em usabilidade (menu touch e web UI).

Repositório: código, esquemáticos simplificados (protoboard), exemplos de firmware, scripts para testes e templates de PoC.



---

Usabilidade para hacking ético (objetivos práticos)

Ferramenta de laboratório para testes controlados em ambiente autorizado.

Funcionalidades previstas (MVP):

Scanner Wi-Fi/BLE (sniffer, visualização de canais).

Sniffer Sub-GHz (captura e replay controlado em ambiente de teste).

Leitor/gravar tags RFID MIFARE (apenas para estudo e testes com autorização).

Emulação IR e replay (TV, A/C — somente dispositivos de propriedade do autor ou com permissão).

Salvar dumps e logs automaticamente no microSD com timestamp.

Interface touch para operar offline + modo web para controle remoto local.


Uso responsável: checklist de autorização, scope e logs para auditoria (sempre documente consentimento em PoCs).



---

Funcionalidades iniciais (MVP)

1. Boot → tela de boas-vindas + splash com versão.


2. Menu: Wi-Fi Scan / BLE Scan / Sub-GHz Sniffer / RFID Reader / Logs.


3. MicroSD: salvar resultados em CSV + arquivos pcap-lite.


4. Network: modo AP para transferir resultados via HTTP simples.


5. Power: monitor de bateria + safe shutdown.



Métricas de sucesso (MVP): boot <5s, salvar log no SD em <2s, captura Sub-GHz básica funcionando em 30m com antena adequada.


---

Ideias e features futuras (roadmap rápido)

V1: MVP (acima) — firmware estável + docs.

V2: UI polida, scripts “apps” (Lua/JS), profiles de teste.

V3: PCB custom + case 3D + boot logo personalizado.

V4: Módulos hot-swap (cartões expandidos), loja de apps para PoCs (scripts assinados).

V5: Hardware rev1 comercial/testado (opcional).



---

BOM (resumo curto — o mínimo para começar)

ESP32-S3 DevKit

TFT 3.2" ILI9341 + XPT2046

Protoboard + jumpers

microSD module (SPI)

CC1101 (sub-GHz) + pigtail/SMA

NRF24L01+ PA/LNA

RC522

Li-Po + TP4056

RTC DS3231, buzzer, botões



---

Considerações legais e éticas (imprenscindível)

Este projeto destina-se a pesquisa e educação. Não use para invasão, intercepção ilícita ou qualquer atividade sem autorização expressa. Inclua sempre: objetivo do teste, escopo, permissão escrita do dono do alvo e logs de auditoria. O repositório inclui um aviso de uso responsável que deve ser lido antes de qualquer uso.
