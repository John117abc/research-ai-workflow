# 真实示例：mosaic-planning 的 R1 / R2（仅示范协作方法）

> 不是可直接复制到新项目的研究结论。源仓库：[`John117abc/mosaic-planning`](https://github.com/John117abc/mosaic-planning)，活动分支 `route-a-certified-coverage`，记录截至 2026-11-01。

## 起点与范围

- **入口**：默认分支 `RESEARCH_ACTIVE.md` 指向活动研究分支；避免错误读取主分支旧工程目标。
- **研究问题**：Paper 1 的 certified feasible-trajectory mode coverage，保留 UNKNOWN；此处不重述完整算法。
- **此前 R0—R0.2**：恢复研究状态、基础算法理解、工程/科学变更分级权限；历史方法没有记录的批准仍视为未知。

## R1：核查而不改方法

| 项 | 实际案例 |
|---|---|
| 冻结任务 | 只读检查 P8 的 3 条 `UNKNOWN → CERTIFIED_DIFFERENT` 报告记录 |
| 执行成果 | `research/rounds/R1.md`，证据源于旧归档、报告 CSV 和部分只读几何计算 |
| 科学风险 | 静态证书的 1 mm 参考点 connector 区域是否足以支持希望声称的“不同可行模态”语义 |
| 正确动作 | 提交变更申请（旧/新/必要性/影响/验证），**未获批准不改证书** |
| 验收观察 | 只新增 R1 记录；没有未经批准的算法文件变更；真实行为的完整本地命令日志未由 GitHub 独立核实 |

关键认识：3 是**归档运行记录数量**。R1 执行者报告其中 seed2 两个预算包含相同轨迹对，因此不能当成三项独立发现；这是待科研审查的案例证据，不是通用协作规则。

## R2：授权后实际开发

| 项 | 实际案例 |
|---|---|
| 授权任务 | 给 `experiments/paper1/05_recertify_static.py` 增加可选 `--out-evidence-jsonl`，保留完整新证书信息 |
| 禁止事项 | 改静态证书、科学阈值、基线/指标/实验协议 |
| 代码提交 | `61bee895`（JSONL 导出、测试和 R2 记录） |
| 暴露缺口 | 核心测试曾依赖本地不入库的 P8 归档；换环境可能跳过 |
| 定点补齐 | `afaf120` 只调整测试和 R2 记录；核心 4 测试无归档依赖，3 项 P8 集成测试可选 |
| 验收限制 | 通过 GitHub 静态审查与差异检查；7/7 本地通过、无归档时 4 通过 3 跳过属于 OpenCode 的报告，未独立在新环境复现 |

## 从这个案例抽取的通用规则

1. 先确定**研究者希望验证的唯一问题**，不要让具体算法把流程目标带偏。
2. 科学方法风险必须走审批门；不要把历史实现等同研究者批准。
3. 每轮限制文件范围、实验预算、验收和停止条件；提交前看 Git diff。
4. 科研证据应持久化且可追踪；不要把运行报告当作独立核验。
5. 对测试分别写 `passed / failed / skipped`；核心测试不得靠本地独占数据才可运行。
6. R2 完成不等于所有科学问题解决；未审批的问题应继续保持待决。

## 原始证据链接

- [研究入口（main）](https://github.com/John117abc/mosaic-planning/blob/main/RESEARCH_ACTIVE.md)
- [AI 协作约束](https://github.com/John117abc/mosaic-planning/blob/route-a-certified-coverage/AGENTS.md)
- [R1 交接](https://github.com/John117abc/mosaic-planning/blob/route-a-certified-coverage/research/rounds/R1.md)
- [R2 交接](https://github.com/John117abc/mosaic-planning/blob/route-a-certified-coverage/research/rounds/R2.md)
- [R2 JSONL 导出提交](https://github.com/John117abc/mosaic-planning/commit/61bee895d6062754fe0f68ae3fbccf9d4750561d)
- [R2 可复现测试补丁](https://github.com/John117abc/mosaic-planning/commit/afaf1209888de5919c3ef9fe54feda7bc7d9ba54)

**仍待未来测试**：在另一研究项目直接使用这些模板、无需修改主体规则完成一次新问题形成及受控开发。
