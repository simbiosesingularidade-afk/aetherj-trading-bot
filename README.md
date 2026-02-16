# 🤖 AetherJ Trading Bot

Trading bot autônomo para criptomoedas com 3 estratégias adaptativas.
Roda 24/7 em VPS com controle total via Telegram.

## 🎯 Estratégias

### 🏆 Major Trend
Captura altas de BTC, ETH, SOL e PAXG usando RSI em múltiplos timeframes.
- Ativa quando o ativo sobe +1.5% a +10% no dia
- RSI 15min < 65 E RSI 1h < 75
- Trailing stop apertado: +1.2% → vende se cai 0.6%

### 🔥 Oversold (Sobrevenda)
Compra valor profundo com dupla confirmação.
- RSI 15min < 30 E RSI 1h < 40
- Qualquer moeda da watchlist
- Maior taxa de acerto histórica

### 🚀 Pump Pullback
Detecta pumps, espera cooldown, compra na correção.
- Detecta alta > 10% com volume > $2M
- Aguarda 3 horas de cooldown
- Compra quando RSI cai abaixo de 42

## 🛡️ Gestão de Risco

| Parâmetro | Valor |
|-----------|-------|
| Stop Loss | -3.0% |
| Take Profit | +5.0% |
| Trailing Stop (Alts) | +1.5% → 0.8% |
| Trailing Stop (Majors) | +1.2% → 0.6% |
| Max Posições | 5 |
| BTC Crash Lock | -4% |
| Max Perda Diária | $12 |

## 📱 Comandos Telegram

| Comando | Função |
|---------|--------|
| `/status` | Visão geral completa |
| `/balance` | Saldo e equity |
| `/positions` | Detalhes das posições |
| `/market` | RSI e tendência do mercado |
| `/strategies` | Estratégias ativas |
| `/forcecheck` | Verifica e executa vendas |
| `/health` | Score de saúde das posições |
| `/report` | Relatório com winrate |
| `/stop` | Para o bot |

22 comandos disponíveis no total.

## ⚙️ Stack Técnica

- **Linguagem:** Python 3
- **Exchange:** Binance via ccxt (async)
- **Análise:** pandas, RSI multi-timeframe
- **Comunicação:** aiohttp + Telegram Bot API
- **Infra:** Ubuntu VPS, nohup
- **Dados:** JSON state persistence


