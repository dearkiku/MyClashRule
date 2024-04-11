## 个人使用说明
**我使用的是[Clash Verge](https://github.com/clash-verge-rev/clash-verge-rev)，这个规则不一定兼容其它版本**  
```yaml
#规则订阅
rule-providers:
 #每间隔{interval}秒访问{url}下载更新到{path}中
  ban:
    #永久拦截无需放行
    type: http
    behavior: domain
    url: https://raw.githubusercontent.com/dearkiku/MyClashRule/main/ban.yaml
    path: ./rules/ban.yaml
    interval: 86400
  ban_AD:
    #去广告 如果网页不能显示需要关闭拦截
    type: http
    behavior: classical
    url: https://raw.githubusercontent.com/dearkiku/MyClashRule/main/ban_AD.yaml
    path: ./rules/ban_AD.yaml
    interval: 86400
  myProxy:
    #需要代理才能访问
    type: http
    behavior: classical
    url: https://raw.githubusercontent.com/dearkiku/MyClashRule/main/myProxy.yaml
    path: ./rules/myProxy.yaml
    interval: 86400
  myDirect:
    #通常情况可直连
    type: http
    behavior: classical
    url: https://raw.githubusercontent.com/dearkiku/MyClashRule/main/myDirect.yaml
    path: ./rules/myDirect.yaml
    interval: 86400
  Server:
    #外网在国内通常可直连的服务
    type: http
    behavior: classical
    url: https://raw.githubusercontent.com/dearkiku/MyClashRule/main/Server.yaml
    path: ./rules/ServerDirect.yaml
    interval: 86400
  Media:
    #媒体
    type: http
    behavior: classical
    url: https://raw.githubusercontent.com/dearkiku/MyClashRule/main/Media.yaml
    path: ./rules/Media.yaml
    interval: 86400
  vMedia:
    #社交媒体
    type: http
    behavior: classical
    url: https://raw.githubusercontent.com/dearkiku/MyClashRule/main/vMedia.yaml
    path: ./rules/vMedia.yaml
    interval: 86400
```
****上下两个可以一起拷贝到正在使用的订阅文件中，（我是在手机端这样使用的****
```yaml
#规则设置
rules:
  #- PROCESS-NAME,update.exe,⭕ 绝对禁止
 #订阅实现
  - RULE-SET,ban,⭕ 绝对禁止
  - RULE-SET,ban_AD,⛔ 广告拦截
  - RULE-SET,myProxy,🚀 节点选择
  - RULE-SET,myDirect,DIRECT
  - RULE-SET,Server,🔗 外网直通
  - RULE-SET,Media,📺 国外媒体
  - RULE-SET,vMedia,📲 社交媒体
```
## 对我来说 - >  
- **ban**是在任何情况下都无用的，可以直接禁止；  
- **ban_AD**是防止网页无法正常显示的时候暂时关闭，这样分类互不影响。  
- **myDirect**是在更多情况下都需要直连的；  
- **myProxy**是在更多情况下都需要代理的。  
- **Server**是在通常情况下都可以**直接使用的外网服务**，为了避免偶尔无法使用的情况下单独建立规则  
- **Media**是外网的媒体，有时候流量不多或其它情况就关掉这个避免流量超额~
- **vMedia**是社交媒体，一般用于通讯类
