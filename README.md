```yaml
proxy-groups:
  - name: PROXY
    type: select
    use:
      - airport
    proxies:
      - DIRECT
  - name: Microsoft
    type: select
    proxies:
      - DIRECT
      - PROXY
  - name: Bilibili
    type: select
    proxies:
      - DIRECT
      - PROXY
rules:
  - DOMAIN,clash.razord.top,DIRECT
  - DOMAIN,yacd.haishan.me,DIRECT
  - RULE-SET,microsoft,Microsoft
  - RULE-SET,bilibili,Bilibili
  - RULE-SET,applications,DIRECT
  - RULE-SET,lancidr,DIRECT
  - RULE-SET,private,DIRECT
  - RULE-SET,customize,DIRECT
  - RULE-SET,icloud,DIRECT
  - RULE-SET,apple,DIRECT
  - RULE-SET,direct,DIRECT
  - RULE-SET,cncidr,DIRECT
  - GEOIP,LAN,DIRECT
  - GEOIP,CN,DIRECT
  - MATCH,PROXY
proxy-providers:
  airport:
    type: file
    path: ./profiles/
    health-check:
      enable: true
      interval: 36000
      url: http://www.gstatic.com/generate_204
rule-providers:
  applications:
    type: http
    behavior: classical
    url: https://raw.githubusercontent.com/Axxxc/clash-rule/master/applications.txt
    path: ./ruleset/applications.yaml
    interval: 86400
  customize:
    type: http
    behavior: classical
    url: https://raw.githubusercontent.com/Axxxc/clash-rule/master/customize.txt
    path: ./ruleset/customize.yaml
    interval: 86400
  microsoft:
    type: http
    behavior: classical
    url: https://raw.githubusercontent.com/Axxxc/clash-rule/master/microsoft.txt
    path: ./ruleset/microsoft.yaml
    interval: 86400
  bilibili:
    type: http
    behavior: classical
    url: https://raw.githubusercontent.com/Axxxc/clash-rule/master/bilibili.txt
    path: ./ruleset/bilibili.yaml
    interval: 86400
  icloud:
    type: http
    behavior: domain
    url: https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/icloud.txt
    path: ./ruleset/icloud.yaml
    interval: 86400
  apple:
    type: http
    behavior: domain
    url: https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/apple.txt
    path: ./ruleset/apple.yaml
    interval: 86400
  proxy:
    type: http
    behavior: domain
    url: https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/proxy.txt
    path: ./ruleset/proxy.yaml
    interval: 86400
  direct:
    type: http
    behavior: domain
    url: https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/direct.txt
    path: ./ruleset/direct.yaml
    interval: 86400
  private:
    type: http
    behavior: domain
    url: https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/private.txt
    path: ./ruleset/private.yaml
    interval: 86400
  gfw:
    type: http
    behavior: domain
    url: https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/gfw.txt
    path: ./ruleset/gfw.yaml
    interval: 86400
  greatfire:
    type: http
    behavior: domain
    url: https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/greatfire.txt
    path: ./ruleset/greatfire.yaml
    interval: 86400
  telegramcidr:
    type: http
    behavior: ipcidr
    url: https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/telegramcidr.txt
    path: ./ruleset/telegramcidr.yaml
    interval: 86400
  cncidr:
    type: http
    behavior: ipcidr
    url: https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/cncidr.txt
    path: ./ruleset/cncidr.yaml
    interval: 86400
  lancidr:
    type: http
    behavior: ipcidr
    url: https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/lancidr.txt
    path: ./ruleset/lancidr.yaml
    interval: 86400
```
