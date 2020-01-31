# DroidBeta Dev Team Git 格式规范

Git 是一个分散式版本控制软件，最初由林纳斯·托瓦兹创作，于2005年以GPL释出。最初目的是为更好地管理Linux核心开发而设计。

DroidBeta Dev Team Git 格式规范有助于更清晰的版本控制管理。本规范由强制规范与建议规范组成。

## 强制规范

* 关于 Commit Message 标记头

每个repo强制使用同一种 Commit Message 标记头是必须的。混乱的标记头会导致版本控制变得混乱无比从而降低工程效率。

相关推荐的标记头将在建议规范中提及。

`待完成` `Waiting to be completed`

### 建议规范

* 关于 Commit Message 标记头

DroidBeta Dev Team 建议使用合理的标记头以合理区分各项 Commit 之间的区别。

以下是 DroidBeta Dev Team 所推荐的两种标记头格式。

| 格式 | 示例 |备注 |
| ------ | ------| ------ |
| $sign: $event | Dev: 升级框架 |使用冒号分隔的类型标记头 |
| [$module] $event | [Dev] 升级框架 | 使用方括号分隔的类型标记头 |
| $part: $event | frame: 修正错误 | 使用冒号分隔的模组标记头 |
| [$module] $event | [frame] 修正错误 | 使用方括号分隔的模组标记头 |

**标记（Sign）推荐内容**
| 内容 | 备注 |
| ----- | ----- |
| Dev | 开发内容，用于新增功能等 |
| Fix | 修正内容，修正错误或漏洞 |
| Opz | 优化代码，优化结构等 |
| Del | 删除代码，去除功能 |

| 内容 | 备注 |
| ----- | ----- |
| Add | 新增代码，功能 |
| Mod | 修改代码，功能 |
| Del | 删除代码，去除功能 |

**模组（Module）推荐内容**

| 内容 | 备注 |
| ----- | -----|
| Frame | 框架 |
| UI | UI |
| Library | 二进制库 |
| `etc` | `其余，待补充` |

无论是怎样等标记头，其标记内容均需使用相同拼写方式，例如完全小写，首字母大写以及完全大写。

```bash
正确示范:
git commit -m "[DEV] Uodate list."
git commit -m "[FIX] Wrong array."

错误示范:
git commit -m "[Dev] Update list."
git commit -m "[dev] Update version."
```
