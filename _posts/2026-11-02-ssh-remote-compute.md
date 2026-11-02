---
layout: post
title:  SSH configure for remote compute
subtitle:   Use compute node by VS Code
date:   2026-11-02
author: HC
header-img: img/post-bg-desk.jpg
catalog: true
tags:
    - SSH
---

I want to use VS Code to do bioinformatics work on compute node, instead of login node. Some configuration should be done.

```
1. 启动并配置Windows SSH 代理服务:
>>> 在 Windows 开始菜单搜索 服务 并打开; 找到 OpenSSH Authentication Agent，右键选择 属性，将启动类型改为 自动，并点击 启动。
>>> 验证：在 PowerShell 中输入 Get-Service ssh-agent，状态应显示为 Running。

2. 将私钥加入到 Windows 代理中:
>>>	打开本地的 PowerShell（或 CMD），执行以下命令：PowerShellssh-add D:\eshell\wanghc666_eshell111.hpccube.com_RsaKeyExpireTime_2027-01-30_12-20-16.txt
>>> 验证：运行 ssh-add -l，如果终端打印出了密钥的指纹信息和路径，说明加载成功。

3. 修改.ssh/config 配置文件:
Host shuguang
    HostName 66666.com
    User wang666
    Port 66666
    IdentityFile xxx_RsaKeyExpireTime_2027-01-30_12-20-16.txt
    ForwardAgent yes

Host compute
    HostName 6.66.6.6
    User wang666
    ProxyJump shuguang
    ForwardAgent yes

>>> 验证：保存文件后，在本地 PowerShell 中手动测试输入 ssh compute。或VS Code连接compute。
```

Enjoy, hope it will be usefull.

