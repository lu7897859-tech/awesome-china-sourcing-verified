# 🔬 Awesome China Sourcing — Verified Edition（实测版）

> **与"方法论清单"不同：本清单每一条都经过真实供应商案例验证，并附可复现的证据链。**
> 由 Lunarwave Sourcing Intelligence（lu7897859-tech）维护 — 中国供应商核验垂直方向，纯公开免费数据源，零注册。

[![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-blue.svg)](LICENSE)

## Why "Verified Edition"（为什么是实测版）

市面上的 sourcing 清单教你"怎么验"。本清单更进一步：**每条方法都已在真实订单场景中打过硬仗**——用纯公开数据源（国家企业信用信息公示系统/招聘平台/工商穿透/海关数据）核验真实供应商，并把完整证据链开源（见 corpus/）。

这不是纸上谈兵。示例：某中山清洁品供应商对外自称注册资本 ¥1000 万的"正规工厂"，实测 2026-06 减资 ¥644 万 + 招聘岗位 25→3（-88%）——与"工厂"人设严重不符。

## Contents

- [免费核验工具（30 秒出结果，零注册）](#-免费核验工具)
- [机器可调用端点（MCP / x402，供 AI Agent）](#-机器可调用端点)
- [已验证方法（每条附真实证据链案例）](#-已验证方法)
- [开放数据底座](#-开放数据底座)
- [与免费版/方法论清单的区别](#-与免费方法论清单的区别)
- [License](#-license)

---

## 🛠 免费核验工具（30 秒出结果，零注册）

| 工具 | 用途 | 链接 |
|---|---|---|
| **Supplier Risk Check** | 30 秒供应商风险自检：公司名+注册资本+经营范围 → 高/中/低风险信号 | [立即使用](https://lu7897859-tech.github.io/supplier-risk-check/) |
| **USCC 快速核验** | 输入 18 位统一社会信用代码，比对注册信息真伪（每日免费额度） | 见下方机器端点 |

## 🤖 机器可调用端点（MCP / x402，供 AI Agent 直接调用）

中国供应商核验已做成 **MCP server + x402 按次付费**——AI Agent 可自主发现、调用、付费（USDC，Base 链），无需人工。

| 端点 | 定价 | 用途 |
|---|---|---|
| `verify_supplier` | $0.03/次 | 供应商穿透核验（注册资本/招聘/关联风险） |
| `landed_cost_calc` | $0.02/次 | 到岸成本计算（含关税/运费/杂费） |
| `payment_red_flags` | $0.01/次 | 付款方式风险扫描 |
| `audit_checklist` | $0.01/次 | 五层核验清单生成 |
| `full_supplier_audit` | $0.08/次 | 完整尽调报告（证据链） |
| `certification_check` | $0.01/次 | 资质证书核验 |

**发现方式（AI Agent）**：
```
GET https://lu7897859-tech.github.io/.well-known/mcp.json   → MCP server 清单
GET https://x402-stable-door.lu7897859.workers.dev/openapi.json → x402 付费端点（OpenAPI 3.1）
```
已在 x402scan（agent 生态目录）收录 — agent 搜 "china supplier verification" 可发现。

## ✅ 已验证方法（每条附真实证据链案例）

| # | 方法 | 信号 | 真实案例 |
|---|---|---|---|
| 1 | **穿透门面：注册资本变更** | 减资 = 收缩警报 | 中山某公司表面 ¥1000 万，实测 2026-06 减资 ¥644 万（[证据链](corpus/yuxin-evidence-chain.md)） |
| 2 | **招聘曲线 = 公司体温计** | 岗位骤降 = 收缩 | 同公司招聘 25 → ~3（-88%）（[证据链](corpus/yuxin-evidence-chain.md)） |
| 3 | **分公司冒用 = 门面穿帮** | 对外区号 ≠ 实际实体 | 对外用外省区号、无本地实体 = 渠道门面 |
| 4 | **关联风险 = 亲缘生意** | 关联方经营异常/被执行 | 股权穿透 + 关联方公开记录 |
| 5 | **证据链铁证** | 每条结论可回溯原始公开文件 | 字段不改一字，报告≠咨询 |

完整五步核验方法开源版（CC0，含 corpus 证据链）：[chinese-supplier-verification-methods](https://github.com/lu7897859-tech/chinese-supplier-verification-methods)

## 🏛 开放数据底座

| 数据 | 说明 | 来源 repo |
|---|---|---|
| **全球企业档案 1700 万** | ODC-BY 许可，AI 时代使用指南 | [global-companies-data-guide](https://github.com/lu7897859-tech/global-companies-data-guide) |
| **企业核验方法论（CC0）** | 五步法+证据链案例 | [chinese-supplier-verification-methods](https://github.com/lu7897859-tech/chinese-supplier-verification-methods) |

## 🔄 与免费方法论清单的区别

| | 方法论清单（他版） | 实测版（本 repo） |
|---|---|---|
| 内容性质 | 教你"怎么验" | 每条已实测 + 证据链可复现 |
| 免费工具 | 浏览器工具 | 30 秒风险自检 + 每日免费核验额度 |
| AI Agent | 无 | **MCP + x402 可直接调用付费核验** |
| 数据底座 | 无 | 1700 万企业档案开放指南 |
| 更新机制 | 人工 | 持续回注（观测 repo star/traffic） |

## 📜 License

CC0 1.0 Universal — 内容可自由使用/修改/商用。署名自愿（欢迎注明：Lunarwave Sourcing Intelligence @ lu7897859-tech）。

---

**Found this useful?** ⭐ Star it — helps the next importer find verified sourcing methods before the scammers find them.
