# clash-rules

个人使用的 Clash / Clash.Meta 代理规则集合。

## 📁 规则分类

| 规则文件 | 说明 |
|----------|------|
| `ai/ai.yaml` | AI 服务代理规则（OpenAI、Claude、Gemini、Copilot 等） |
| `company/company_direct.yaml` | 公司内网直连规则 |
| `company/company_proxy.yaml` | 公司相关服务代理规则（钉钉、阿里云等） |
| `company/company_reject.yaml` | 公司相关拒绝规则 |
| `custom/custom_direct.yaml` | 自定义直连规则 |
| `custom/custom_proxy.yaml` | 自定义代理规则 |

## 🚀 使用方法

### Clash.Meta / Mihomo

在配置文件中添加规则提供者：

```yaml
rule-providers:
  ai:
    type: http
    behavior: classical
    url: "https://raw.githubusercontent.com/chenzhiguo/clash-rules/main/ai/ai.yaml"
    path: ./ruleset/ai.yaml
    interval: 86400

  custom-direct:
    type: http
    behavior: classical
    url: "https://raw.githubusercontent.com/chenzhiguo/clash-rules/main/custom/custom_direct.yaml"
    path: ./ruleset/custom_direct.yaml
    interval: 86400

  custom-proxy:
    type: http
    behavior: classical
    url: "https://raw.githubusercontent.com/chenzhiguo/clash-rules/main/custom/custom_proxy.yaml"
    path: ./ruleset/custom_proxy.yaml
    interval: 86400
```

然后在规则中引用：

```yaml
rules:
  - RULE-SET,ai,🤖 AI
  - RULE-SET,custom-direct,DIRECT
  - RULE-SET,custom-proxy,🚀 Proxy
```

## 📝 许可证

[MIT License](./LICENSE)
