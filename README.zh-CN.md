# Polymarket 做市机器人 | 自动化 CLOB 做市，获取被动交易收益

**Language / 语言:** [English](README.md) | [中文](README.zh-CN.md)

> **联系方式：** [Telegram @movez_x](https://t.me/movez_x)

---

## 这是什么机器人？

**Polymarket 做市机器人** 是一个自动化做市程序，在 [Polymarket](https://polymarket.com) 的 CLOB（中央限价订单簿）上提供流动性。它会持续围绕中间价挂单和撤单，通过做市赚取买卖价差，同时帮助其他交易者成交。

无论你是预测市场爱好者，还是希望获得被动收入的 DeFi 交易者，这款机器人都可以 24/7 运行，在 Polymarket 上赚取做市收益。

---

## 交易者的 5 大优势

| # | 优势 | 说明 |
|---|------|------|
| 1 | **被动收入** | 自动赚取买卖价差。资金为你工作，无需手动交易。 |
| 2 | **24/7 自动化交易** | 机器人持续监控订单簿，每 30 秒（可配置）重新平衡订单。无需盯盘或手动下单。 |
| 3 | **两种专业策略** | 可选 **AMM**（集中流动性风格）或 **Bands**（多档位挂单）。每种策略都有可调参数，适应不同风险偏好。 |
| 4 | **完全控制与透明** | 开源代码，可配置价差、深度和抵押品上限。你决定投入多少资金、报价多紧。 |
| 5 | **优雅退出** | 退出时（SIGTERM）会取消所有未成交订单并安全退出，不会留下孤儿订单。 |

---

## 获取完整代码、定制功能、帮助或高级版

- **完整源码** – 本仓库包含核心机器人。如需扩展功能或定制版本，请联系我们。
- **添加功能** – 需要新策略、多市场支持或集成？我们可以协助开发。
- **技术支持** – 在安装或配置上遇到问题？可向团队寻求帮助。
- **高级版** – 如需高级功能、专属支持或托管部署，请联系我们。

**Telegram 联系：** [@movez_x](https://t.me/movez_x)

---

## 快速开始 – 运行机器人

### 环境要求

- Python 3.10
- Polymarket 账户及 USDC（Polygon 链）
- 目标市场的 Condition ID

### 1. 安装

```bash
./install.sh
```

将创建虚拟环境并安装依赖。

### 2. 配置环境变量

创建 `.env` 文件（参考 `.env.example`）：

```
PRIVATE_KEY=你的私钥
RPC_URL=https://polygon-rpc.com
CLOB_API_URL=https://clob.polymarket.com
```

### 3. 配置市场与策略

编辑 `config.env`：

```
CONDITION_ID=0x...   # Polymarket 市场的十六进制 Condition ID
STRATEGY=amm         # 或 "bands"
CONFIG=./config/amm.json   # 或 ./config/bands.json
```

根据需要调整 `./config/amm.json` 或 `./config/bands.json` 中的策略参数。

### 4. 运行

```bash
./run-local.sh
```

### Docker 方式（可选）

```bash
docker compose up
```

---

## 策略概览

| 策略 | 说明 |
|------|------|
| **AMM** | 集中流动性风格——在多个价格档位挂单，可配置价差、delta 和深度。详见 [docs/strategies/amm.md](docs/strategies/amm.md)。 |
| **Bands** | 多档位策略——在指定价格区间和数量范围内维持订单。详见 [docs/strategies/bands.md](docs/strategies/bands.md)。 |

默认每 30 秒同步一次：获取中间价、计算目标订单、撤销过期订单并挂出新订单。

---

## 免责声明

本软件处于实验阶段，持续开发中。使用风险自负。请先用小额资金测试。

---

## 联系方式

**Telegram：** [@movez_x](https://t.me/movez_x)

---

## English Version

[View English README → README.md](README.md)
