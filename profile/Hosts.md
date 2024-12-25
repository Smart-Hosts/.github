# Hosts File

```hosts
# This is a sample hosts file used by Smart Hosts.
127.0.0.1 example.com
192.168.1.1 nas.home, ssid="home" # NAS server LAN address for LAN network
100.64.0.1 nas.home # NAS server Tailscale address for WAN network
```

## Rule Composition

- **Action**
  - IPv4 address
- **Domain**
  - A single domain
  - Multiple domains separated by commas
  - Supports Unix shell-style wildcards
- **Condition**
  - `ssid` matches the current network's Wi-Fi SSID

Each rule occupies one line. The text before the first space is the **Action**,
and the text after the space is the **Domain**,
which can include multiple domains separated by white spaces.
Domains support Unix shell-style wildcards, such as `*-nas.home`.
Parameters after a comma act as optional **Conditions**.
Currently, the supported condition is `ssid="home"`,
which distinguishes between different Wi-Fi network environments.

You can also use the `#` symbol at the beginning of a line to add comments.

Rules are matched sequentially from top to bottom.
Matching stops as soon as the first rule is applied.
