# 📡 Projeto de Correção de Interferência FM em Sistema CFTV Analógico

![Status](https://img.shields.io/badge/status-em%20andamento-yellow)  
![CFTV](https://img.shields.io/badge/CFTV-analógico-blue)  
![Infraestrutura](https://img.shields.io/badge/cabeamento-coaxial%20%2B%20UTP%20cat5e-lightgrey)  
![Licença](https://img.shields.io/badge/licença-MIT-green)

## 🎯 Objetivo
Mitigar interferência de **rádio FM (88–108 MHz)** em sistema de **CFTV totalmente analógico**, instalado a **500 m de torre transmissora**, utilizando cabeamento **misto coaxial 75 Ω** e **UTP Cat 5e com vídeo-baluns**.  
O projeto documenta **diagnóstico, ações corretivas e boas práticas**, servindo como guia para profissionais de campo.

---

## 🛠 Cenário
- 📍 Distância de ~500 m da torre FM.  
- 🎥 Sistema **100% analógico (CVBS)**.  
- 🔌 Cabeamento: coaxial 75 Ω e UTP Cat 5e com baluns.  
- ⚡ Problema: barras horizontais, ondulações e perda de qualidade de vídeo causadas por acoplamento de RF.

---

## 🔍 Diagnóstico de Interferência
1. **Acoplamento em modo comum**: cabos funcionando como antenas.  
2. **Baluns de baixa qualidade**: baixo CMRR, pouco equilíbrio.  
3. **Blindagem deficiente**: malhas soltas, conectores inadequados.  
4. **Aterramento inadequado**: correntes de retorno pela malha.  
5. **Fontes de alimentação baratas**: sem filtragem EMI.

---

## 🧩 Solução — Estratégia em 6 Fases

### 1. Levantamento
- Mapeamento das rotas dos cabos.  
- Testes de aterramento e continuidade.  
- Osciloscópio/analisador de espectro para verificar RF (88–108 MHz).  

### 2. Cabeamento & Conectividade
- Padronização em coax **RG-6/59 quad-shield** + conectores compressão.  
- **Ground blocks** na entrada do rack.  
- Baluns ativos de **alto CMRR** em enlaces longos.  
- Uso de **FTP/STP Cat 5e** em áreas críticas.  

### 3. Blindagem & Roteamento
- Passagem em **eletroduto metálico contínuo** ligado ao PE.  
- Travessias de energia **perpendiculares e curtas**.  
- Zero “stubs” (sem T).  

### 4. Filtragem EMI
- Núcleos de **ferrite mix 31/43** em coax e UTP.  
- **Filtros passa-baixa** até 10–20 MHz antes do DVR.  
- **Notch 88–108 MHz** para enlaces críticos.  
- Substituição por **fonte centralizada filtrada** + **SPD** na entrada.  

### 5. Aterramento & Equipotencialização
- **Barramento equipotencial** no rack.  
- Interligação com PE do quadro elétrico (≥16 mm²).  
- Continuidade <0,5 Ω entre rack e PE.  
- Resistência de aterramento ≤10 Ω.  

### 6. Segmentação por Fibra (opcional)
- Conversores A/F para enlaces mais críticos.  
- Fibra quebra o caminho da RF e elimina o acoplamento.  

---

## 📋 Materiais Principais
- Coaxial RG-6/59 quad-shield + conectores compressão.  
- UTP FTP/STP Cat 5e.  
- Baluns ativos com CMRR ≥60 dB.  
- Núcleos de ferrite (mix 31/43).  
- Filtros passa-baixa (0–20 MHz) e notch FM.  
- Fonte centralizada de baixa ondulação + filtro EMI.  
- SPD Classe II (energia) e SPD a gás (coax).  

---

## ✅ Testes de Aceitação
- Eliminação visível de barras/ondulações.  
- Redução ≥20 dB em RF na faixa 88–108 MHz.  
- Ripple de energia <50 mVpp sob carga.  
- Continuidade de PE <0,5 Ω.  
- DVR recebendo sinal limpo e estável em todas as câmeras.  

---

## 📂 Estrutura do Repositório
```text
.
├── README.md   # Documento principal do projeto
├── docs/
│   ├── diagrama_logico.png
│   ├── checklist_execucao.md
│   ├── materiais_recomendados.md
│   └── testes_validacao.md
└── LICENSE
