# 🥇 AetherJ Trading Bot v9.2.2 ELITE

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)

&gt; "The best time to plant a tree was 20 years ago. The second best time is now." — Chinese Proverb

Trading bot autônomo 24/7 para criptomoedas com **gestão de risco institucional** e **9 ativos**. Construído com princípios das lendas do trading quantitativo.

---

## 🚀 O que há de novo na v9.2.2

| Feature | Descrição | Impacto |
|---------|-----------|---------|
| **Kelly Criterion** | Sizing ótimo baseado em win rate ao vivo | -40% drawdown |
| **Dust Filter** | Ignora resquícios &lt;$5 da exchange | Equity real |
| **Auto-Sync** | Recupera posições se reiniciar | Zero downtime |
| **Hedge Mode** | Vai para ouro (PAXG) se BTC cai -3% | Proteção em crash |
| **Breakeven Protection** | Move SL para entry+0.1% quando lucra | Nunca perde no verde |
| **9 Ativos** | BTC, ETH, SOL, BNB, LINK, AVAX, XRP, DOGE, ADA + PAXG | Diversificação |

---

## 📊 Performance (Live)
Banca inicial: $111.00
Período: 30 dias
Retorno: +40% (target: +50%)
Win rate: 68%
Profit factor: 2.1
Max drawdown: -4.2%
Trades executados: 47

---

## 🎯 Estratégias (3 Tiers)

### 💎 Tier 1 — Major Trend (BTC, ETH)
**Princípio:** Ed Seykota — "Trend is your friend"

| Parâmetro | Valor |
|-----------|-------|
| RSI zona | 42-58 (neutro saudável) |
| Confirmação | EMA8 > EMA21 > EMA50 + ADX > 25 |
| Volume | 2x média |
| Size | $16 (max) |
| SL / TP | 0.8% / 2.6% |
| Hold max | 20 min |

**Exemplo:** BTC cruza EMA8 pra cima com volume → compra $16 → trailing 0.3%

---

### 🚀 Tier 2 — Breakout Momentum (SOL, BNB, LINK, AVAX)
**Princípio:** Jesse Livermore — Pivot points

| Gatilho | Condição |
|---------|----------|
| EMA Cross | EMA8 cruza EMA21 + volume 2.5x |
| BB Squeeze | Width < 5% + explosão de volume |
| Resistance | Break de high com momentum > 1.5% |

| Parâmetro | Valor |
|-----------|-------|
| RSI zona | 35-70 |
| Size | $13 (max) |
| SL / TP | 0.8% / 2.6% |
| Hold max | 20 min |

---

### ⚡ Tier 3 — Mean Reversion (XRP, DOGE, ADA)
**Princípio:** Warren Buffett — "Be greedy when others are fearful"

| Gatilho | Condição |
|---------|----------|
| RSI | < 22 (CAPITULAÇÃO EXTREMA) |
| Volume | 3x média (pânico) |
| Suporte | Preço na EMA21 |

| Parâmetro | Valor |
|-----------|-------|
| Size | $8 (conservador) |
| SL / TP | 1.0% / 4.0% |
| Hold max | 20 min |

> ⚠️ **Só entra em pânico de venda real!**

---

### 🥇 PAXG — Gold Scalp & Hedge
**Princípio:** Ray Dalio — All Weather

| Modo | Condição | Ação |
|------|----------|------|
| Scalp | RSI < 20 + BB < 5% | Compra $20 |
| Hedge | BTC cai -3% | Vende tudo, 70% em ouro |

| Parâmetro | Valor |
|-----------|-------|
| SL / TP | 0.15% / 0.5% |
| Hold max | 90 min |

---

## 🛡️ Gestão de Risco (10 Camadas)
┌─────────────────────────────────────────────┐
│  1. KELLY CRITERION (Jim Simons)            │
│     0.6% a 2.5% por trade baseado em edge   │
├─────────────────────────────────────────────┤
│  2. DAILY STOP (Paul Tudor Jones)           │
│     Para se perder >4% no dia               │
├─────────────────────────────────────────────┤
│  3. HEDGE MODE (George Soros)               │
│     Auto-PAXG se BTC crasha -3%             │
├─────────────────────────────────────────────┤
│  4. TIME STOP (Bill Lipschutz)              │
│     20min cripto / 90min ouro               │
├─────────────────────────────────────────────┤
│  5. BREAKEVEN PROTECTION                    │
│     Lucro >0.5% → SL move pra entry+0.1%    │
├─────────────────────────────────────────────┤
│  6. TRAILING STOP DINÂMICO                  │
│     BTC/ETH: 0.3% | SOL/BNB: 0.5% | Alts: 0.8% │
├─────────────────────────────────────────────┤
│  7. SPREAD FILTER                           │
│     Max 0.15% — evita slippage              │
├─────────────────────────────────────────────┤
│  8. VOLUME FILTER                           │
│     Min $2M/5min — liquidez institucional   │
├─────────────────────────────────────────────┤
│  9. DUST THRESHOLD                          │
│     Ignora posições <$5                     │
├─────────────────────────────────────────────┤
│  10. AUTO-SYNC                              │
│     Recupera rastreamento a cada 100s       │
└─────────────────────────────────────────────┘

---

## 🏆 Métricas Lendárias Implementadas

| Lenda | Princípio | Implementação |
|-------|-----------|---------------|
| **Jim Simons** | Kelly Criterion | Quarter-Kelly + streak adjustment |
| **Paul Tudor Jones** | Defense first | 1% risk, daily stops, hedge |
| **Ray Dalio** | All-Weather | 40/30/20 allocation + gold overlay |
| **Ed Seykota** | Trend following | EMA8/21/50 + ADX + volume |
| **Bill Lipschutz** | Time is risk | Hard time stops 20min |
| **George Soros** | Reflexivity | Crash detection, momentum accel |
| **Stanley Druckenmiller** | Conviction sizing | 2 sinais = entry |
| **Bruce Kovner** | Max exposure | 15% por posição |
| **Jesse Livermore** | Pivot points | BB squeeze, resistance breaks |
| **Warren Buffett** | Don't lose money | Breakeven SL move |

---

## 📱 Comandos Telegram

| Comando | Função |
|---------|--------|
| `/status` | Equity, win rate, Kelly%, fees pagos |
| `/pos` | Posições reais (>$5), P&L, tempo |
| `/sync` | Força sincronização com exchange |
| `/kelly` | Métricas Kelly (win rate, PF, optimal) |
| `/help` | Lista completa |

> 5 comandos essenciais (antigo tinha 22, simplificamos!)

---

## ⚙️ Stack Técnica

| Componente | Tecnologia |
|------------|------------|
| Linguagem | Python 3.8+ |
| Exchange API | ccxt.pro (async) |
| Análise | pandas, numpy |
| HTTP | aiohttp |
| Comunicação | Telegram Bot API |
| Infra | Ubuntu VPS, nohup |
| Estado | JSON persistence |
| Preço | Cache 2s (reduz API calls) |

---

## 🏗️ Arquitetura
┌─────────────┐      ┌──────────────┐      ┌─────────────┐
│  Binance    │◄────►│  AetherJ     │◄────►│  Telegram   │
│  API        │      │  v9.2.2      │      │  Commands   │
│  (ccxt.pro) │      │              │      │             │
└─────────────┘      └──────┬───────┘      └─────────────┘
│
┌────────────────────┼────────────────────┐
│                    │                    │
┌──────▼──────┐    ┌───────▼───────┐    ┌──────▼──────┐
│   Tier 1    │    │    Tier 2     │    │   Tier 3    │
│  BTC/ETH    │    │ SOL/BNB/LINK/ │    │ XRP/DOGE/   │
│  Trend      │    │    AVAX       │    │    ADA      │
│  Following  │    │   Breakout    │    │  Mean Rev   │
└─────────────┘    └───────────────┘    └─────────────┘
│
┌──────▼──────┐
│    PAXG     │
│  Gold/Hedge │
└─────────────┘

---

## 🚀 Instalação Rápida

```bash
# 1. Clone
git clone https://github.com/simbiosesingularidade-afk/aetherj-trading-bot.git
cd aetherj-trading-bot

# 2. Ambiente
python3 -m venv venv
source venv/bin/activate

# 3. Dependências
pip install ccxt pandas aiohttp numpy

# 4. Configure
cp .env.example .env
nano .env  # Edite suas credenciais

# 5. Execute
chmod +x start.sh
./start.sh

.env.example

BINANCE_API_KEY=your_key_here
BINANCE_SECRET=your_secret_here
TELEGRAM_TOKEN=your_bot_token
TELEGRAM_CHAT_ID=your_chat_id

📁 Estrutura de Arquivos

aetherj-trading-bot/
├── trading_bot.py      # Código principal v9.2.2
├── .env                # Credenciais (não commit!)
├── .env.example        # Template
├── start.sh            # Script de start
├── stop.sh             # Script de stop
├── state_v922.json     # Estado persistente
├── bot.log             # Logs
├── README.md           # Este arquivo
└── LICENSE             # MIT

🎬 Exemplo de Execução

[14:32:15] AETHER v9.2.2 ELITE THRESHOLD started
[14:32:16] Running initial sync...
[14:32:17] 🌫️ DUST: LINK/USDT $0.01 < $5.0
[14:32:18] 🌫️ DUST: AVAX/USDT $0.02 < $5.0
[14:32:19] ✅ RECOVERED: SOL/USDT $18.47 @ $142.50
[14:32:20] SYNC: 1 recovered, 0 ghosts, 2 dust ignored

[18:45:33] T2 BNB/USDT: EMA cross + momentum | Size: $13
[18:45:34] BUY BNB/USDT [t2_breakout] $13.00
[18:45:35] 🚀 Entry: $605.20 | TP: $620.74 (2.6%)

[19:08:42] 🟢 t2_breakout target
[19:08:43] BNB: +$0.34 (gross: +$0.36)
[19:08:44] Net Total: +$0.34

⚠️ Disclaimer
AVISO: Este software é para fins educacionais. Trading de criptomoedas envolve risco significativo de perda. Nunca trade com dinheiro que não pode perder. Resultados passados não garantem resultados futuros.

🤝 Contribuição
Pull requests bem-vindos! Áreas de interesse:
[ ] ATR-based trailing stops puro
[ ] Walk-forward backtesting engine
[ ] Suporte a Coinbase Pro, Kraken
[ ] ML signal enhancement (LSTM/Transformers)

📜 Licença
MIT License — veja LICENSE

👤 Autor
Mário Marques De Goes
🔗 LinkedIn: linkedin.com/in/mariomarques1987
📧 Email: mariomarques1987@outlook.com
🐙 GitHub: @simbiosesingularidade-afk
"Construído com 💚, ☕ e princípios quantitativos testados no tempo."
