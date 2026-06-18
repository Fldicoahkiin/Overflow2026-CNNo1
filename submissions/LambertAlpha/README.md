# LadderVault

## Track / 赛道

- [ ] Agentic Web
- [ ] DeFi & Payments
- [x] DeepBook
- [ ] Walrus

## Description / 项目简介

**LadderVault is an active risk-managed LP vault for DeepBook Predict.**

Passive prediction-market LPs earn making fees but are *passive*: when traders pile positions onto a hot strike and the price pins there, those positions settle in the money together and the LP eats an asymmetric tail loss. LadderVault monitors a **concentration signal** (`pin_risk` = payout at the current price level ÷ total inventory) and **automatically withdraws** from Predict when risk spikes, re-entering once it subsides. In our offline kill-test this cuts the worst-case drawdown from **-13.4% (passive) to -0.1% (active) — an 82% tail reduction that approaches the look-ahead Oracle upper bound — without any directional prediction.**

**（中文）** LadderVault 是 DeepBook Predict 上的主动风险管理 LP 金库。被动 LP 在"价格黏在某热门行权价、库存集中中标"时被尾部赔付击穿;LadderVault 用集中度信号在风险堆积时自动从 Predict 撤出、平静后回场,把最坏回撤从 -13.4% 削到 -0.1%(削尾 82%,逼近先知上界),且不依赖任何方向性预测。量化护城河经完整链下验证,合约已部署 testnet 并跑通端到端交易。

## Links / 链接

- GitHub: https://github.com/LambertAlpha/LadderVault
- Demo Video: _(待录制 / TODO — YouTube, ≤ 5 min)_
- DeepSurge: _(待补 / optional)_

## Team / 团队成员

- @LambertAlpha

## Deployment / 部署信息

- Env: **Testnet**
- Package ID: `0x1f6134b78470a5d6818e956b53140850a2501f122839d80e6d8d60877e3cc52d`
- Vault\<SUI\>: `0x0906b259c177763e0898fb8135b608938676de047bf153971d60fdf07034341b`
- PredictPool\<SUI\>: `0xa9a8a407f4f1698e28a6290e0b800a2bbafed8012bf6587f2eafe0fa202ac17d`

> 注:demo 使用对齐真实 DeepBook Predict 接口(`supply`/`withdraw`/range)的简化 `predict_mock`,因官方 Predict 链上设施在赛期尚未完成;赛后第一步即切换真实 Predict。

## Swag / 周边

- [x] 我希望接收周边 / I'd like to receive swag
