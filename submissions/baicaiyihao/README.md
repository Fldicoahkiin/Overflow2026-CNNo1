# SUI Intent Engine / SUI 意图引擎

> 自然语言 → 6 维 Guardian 风险守护 → 人类可读 PTB 预览 → 钱包签名 → DeepBook V3 主网执行
> Natural language → 6-dimension Guardian risk check → human-readable PTB preview → wallet-signed DeepBook V3 execution on Sui mainnet.

## Track / 赛道

- [x] Agentic Web
  - **Sub-track 3: Intent Engine**

> Sub-track 3 要求：`text → PTB → execution` + 人类可读 PTB 预览 + Guardian ≥ 2 风险类 + 显式确认。本项目 Guardian 已覆盖 **6 维风险**（RSI · MACD · Bollinger · KDJ · Volume · ADX），远超要求。

## Description / 项目简介

SUI Intent Engine 是为 Sui 原生 CLOB (DeepBook V3) 设计的 **意图引擎**。用户用自然语言描述交易意图（例：*"RSI 低于 30 时买入 100 USDC SUI，2% 滑点容忍"*），引擎在 4 步内完成从话语到链上执行的闭环：

1. **PARSE** — LLM 解析为结构化意图（动作 / 金额 / 价格 / 触发条件）
2. **GUARD** — Guardian 跑 6 维技术指标风险检查，揭示滑点 / 弱趋势 / 低流动性 / 趋势反转
3. **PREVIEW** — 人类可读 PTB 卡片（价格、数量、总成本、过期时间、余额校验，无黑盒）
4. **SIGN** — 用户显式确认，钱包签名，DeepBook V3 在 Sui 主网执行

**为什么是 Sub-track 3 而不是 chatbot**：
- Guardian 是产品差异化（不是 LLM 包装）
- 钱包签名 + 显式 confirm = 用户始终在环
- 真实链上执行（不是模拟），BalanceManager 生命周期完整

**已实现技术亮点**：
- 自研 i18n 框架（zh + en，27 落地页 key + 300+ 应用 key，EN 默认）
- Bilingual LLM prompt 字典（按 locale 自动切换中英 prompt，避免 "EN UI 出中文答案"）
- Bloomberg Terminal 风格落地页 + 实时 SUI/USDC 行情面板
- 已在 Sui 主网验证 7+ 笔真实交易（限价单 / 市价单 / 存款 / 提取）
- 全部 TypeScript + React + Vite 前端，Python FastAPI 后端

**商业化路径**：
1. DeepBook V3 手续费返佣（0.05–0.10%/笔）
2. 订阅制 AI 信号（Free / Pro $29 / Pro+ $99）
3. 策略市场（70/30 订阅分成，链上战绩溯源）
4. B2B API 接入（卖给其他 DeFi 前端）

## Links / 链接

- GitHub: https://github.com/baicaiyihao/sui-intent-engine
- 项目主页 (Landing Page): https://github.com/baicaiyihao/sui-intent-engine#readme
- Demo Video: 即将补充 / To be added
- Website: 暂未上线 / Not launched yet

> 官方要求的 Demo 视频将通过新 PR 在提交截止前补充。
> Demo video (≤ 5 min) will be added via a follow-up PR before the submission deadline.

## Team / 团队成员

- @baicaiyihao

## Deployment / 部署信息

- **Env: Mainnet** (SUI 主网)
- **项目自身未部署 Move 合约**，调用以下 Sui 原生 / 生态合约：

| 合约 | Package ID | 用途 |
|---|---|---|
| DeepBook V1 (Pool) | `0x2c8d603bc51326b8c13cef9dd07031a408a48dddb541963357661df5d3204809` | 限价单 / 市价单 / 提现 / claim |
| Cetus DeepBook Utils | `0x600138d3179e2fc746f6774f360a6e1fa68e90d66d082af66399adabe46f22a4` | 一笔 PTB 完成 deposit + place order |
| DeepBook V3 Global Config | `0xff1141ef80e7baf206c7930c274b465600e64884d8167f90d4cdb60197925163` | Cetus utils 调用入口 |
| SUI/USDC Pool | `0xe05dafb5133bcffb8d59f4e12465dc0e9faeaa05e3e342a08fe135800e3e4407` | 真实交易池 |

- 测试钱包：`0xc52aa1eb1eca93287966af0f12d5fce3b959d3ae598673b90e539987916bc64e` (仅用于开发期测试，用户生产环境用自己的钱包)
- 已验证交易详见 `AGENTS.md` 内 "已验证信息" 章节

## Swag / 周边

- [x] 我希望接收周边 / I'd like to receive swag
  > 大陆收货地址，收件信息将通过周边收件表单单独提交，不在公开 PR 中暴露隐私。
  > Mainland China shipping address. Recipient info will be submitted separately via the swag form, not exposed in the public PR.
