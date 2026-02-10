# 🦞 Dragon Quant Lab — DOGE/BTC 量化策略

## 策略总览

基于 MEXC 交易所 DOGE/USDT 和 BTC/USDT 永续合约的量化交易策略。
使用 TradingView Pine Script 编写，5分钟时间框架。

### 策略A：MTF_RSI 稳健滚仓版 🛡️

**文件**: `strategies/Strategy_A_MTF_RSI_Stable.pine`

| 指标 | 数值 |
|------|------|
| 回测收益 | $1,000 → $6,440 (6.44x) |
| 胜率 | 35.7% |
| 最大回撤 | 15.3% |
| 交易频率 | ~0.3次/天 |
| 信号逻辑 | RSI(14)+RSI(6) 极值 + BTC RSI 联动 + 放量 + K线确认 |
| 杠杆 | 底仓10x → 加仓50x/100x/200x |
| 止损/止盈 | 1.5 ATR / 3.0 ATR |

### 策略B：Composite 暴利滚仓版 💣

**文件**: `strategies/Strategy_B_Composite_Aggressive.pine`

| 指标 | 数值 |
|------|------|
| 回测收益 | $1,000 → $26,284,254 (26,284x) |
| 胜率 | 23.7% |
| 最大回撤 | 72.2% ⚠️ |
| 交易频率 | ~5次/天 |
| 信号逻辑 | 12因子评分 (RSI/MACD/BB/Volume/趋势 × 4个时间框架) |
| 杠杆 | 底仓10x → 加仓50x/100x/200x |
| 止损/止盈 | 2.5 ATR / 5.0 ATR |

## 使用方法

1. 打开 TradingView → Pine Editor
2. 粘贴对应 `.pine` 文件的完整代码
3. 选择 `MEXC:DOGEUSDT.P` (DOGE永续合约)
4. 时间框架选择 **5分钟**
5. 点击"添加到图表"

## 数据来源

回测使用以下数据（2025-09 至 2026-02）：
- MEXC BTC/USDT: 1分钟、5分钟、15分钟、日线
- MEXC DOGE/USDT: 1分钟、5分钟、15分钟、日线

## ⚠️ 风险提示

- **策略A** 适合稳健增长，回撤可控
- **策略B** 极端激进，72%回撤意味着可能亏掉大部分本金
- 回测结果不代表未来表现
- 建议先用模拟盘验证
- 实盘建议从小资金开始

## 回测引擎

Python 回测代码位于 `backtest_v9.py`，使用全部 8 个数据集进行多时间框架分析。

---
*Built by 🦞 Dragon Quant Lab*
