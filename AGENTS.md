# AGENTS.md

这个仓库用于维护 Stash iOS 覆写规则。

## 主要文件

Stash iOS 使用的主覆写文件。

## 修改要求

- 保持 YAML 语法正确。
- `proxy-groups` 必须使用 `#!replace`，用于完全替换订阅自带策略组。
- `rules` 必须使用 `#!replace`，避免订阅原规则混入。
- Copilot 必须继续走 `AIGC`。
- Apple 服务默认直连。
- Microsoft 大部分服务默认直连，但 Copilot 例外。
- 新增 rule-provider 后，必须检查 `rules` 是否引用了正确名称。
- 更具体的规则放在更通用规则前面。
- `geolocation-!cn` 和 `MATCH` 放在靠后位置。

## 修改后检查

1. `rules` 中引用的策略组都存在。
2. `rules` 中引用的 rule-provider 都存在。
3. `copilot` 规则位于 `microsoft` 规则之前。
4. Stash raw 链接仍然指向 `.stoverride` 文件。
