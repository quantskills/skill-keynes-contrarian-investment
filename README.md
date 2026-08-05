# 凯恩斯长期预期与反共识投资 Skill

> 不知道怎么提问？查看 [`可以问什么.md`](./可以问什么.md)，其中包含单股分析、介入时点、价值陷阱、多股比较、持仓体检、历史复盘和兆易创新完整提问模板。

## 快速开始

```bash
python3.11 scripts/expectation_contrarian.py \
  --symbol 600519.SH \
  --out-json /tmp/keynes_600519.json \
  --out-md /tmp/keynes_600519.md
```

批量使用指数股票池：

```bash
python3.11 scripts/expectation_contrarian.py --universe csi300 --top-n 20
```

先探测当前 PandaData 账号的接口和字段：

```bash
python3.11 scripts/expectation_contrarian.py --symbols 600519.SH --probe-only
```

凭证配置：环境变量优先，也可配置 `~/.pandadata/pandadata.env`：

```text
PANDA_USERNAME=...
PANDA_PASSWORD=...
```

## 研究逻辑

长期预期不是精确预测；市场共识在没有正式一致预期字段时只能用历史估值、公司业绩预告和市场行为做代理。Skill 首先判断企业性投资的基本面耐久性，然后分析价格隐含预期和安全边际，最后考察市场定位、催化剂与证伪条件。

低估值但盈利与现金流同步恶化的标的不会因为“便宜”自动入选。

## 输出

- JSON：指标、公式、状态、日期、评分、否决门、代理限制和 provenance；
- Markdown：中文研究报告；
- N/A：接口空、错误或不支持时保留章节并显示原因。

运行测试：

```bash
python3.11 -m pytest tests -q
```
