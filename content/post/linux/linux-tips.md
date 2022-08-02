---
title: "Linux Tips"
date: 2022-08-02T11:17:56+08:00
draft: false
---

- CentOS 8 配置静态 ip 后，拔掉网线不会更改网络连接状态  
配置`ignore-carrier=no`选项，如`echo ignore-carrier=no >>/etc/NetworkManager/conf.d/00-server.conf`，参考`https://people.freedesktop.org/~lkundrak/nm-docs/NetworkManager.conf.html`

- 禁用编入内核的驱动  
以`i40e`为例，在源码中搜索`module_init`关键字对应的名字是`i40e_init_module`，引导参数添加`initcall_blacklist=i40e_init_module`，参考`https://www.kernel.org/doc/Documentation/admin-guide/kernel-parameters.txt`
