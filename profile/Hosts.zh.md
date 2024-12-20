# Hosts 文件

```hosts
# This is a sample hosts file used by Smart Hosts.
127.0.0.1 example.com
192.168.1.1 nas.home, ssid="home" # NAS server Lan address for Lan network
100.64.0.1 nas.home # NAS server Tailscale address for Wan network
```

## Rule 的组成

- Action
  - IPv4 地址
- Domain
  - 单个域名
  - 多个域名，使用逗号分隔
  - 可使用 Unix Shell 风格的通配符
- Condition
  - ssid 匹配当前网络 Wi-Fi 的 ssid

一行一个规则，第一个空格前为 Action，空格后为 Domain ，可以使用逗号分隔多个 Domain 。
Domain 支持 Unix Shell 风格通配符, 例如 `*-nas.home` 。
后面以 `,` 来分割的参数为可选参数 Condition ，
目前支持 `ssid="home"` 参数，用于区分不同的 Wi-Fi 网络环境。
每行也可以使用 # 符号开头来增加注释。

规则的匹配顺序是从上到下，匹配到第一个规则后就停止匹配。

