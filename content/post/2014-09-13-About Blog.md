---
date: 2014-09-13T18:20:31+08:00
title: About Blog
tags: ["blog"]
---

开源:<https://github.com/zhu327/blog>  
Boz是一个用Python实现的轻量级Blog程序。    
这是一个练习作品，开始于[廖雪峰的Python教程实战篇](http://www.liaoxuefeng.com/wiki/001374738125095c955c1e6d8bb493182103fac9270762a000/001397616003925a3d157284cd24bc0952d6c4a7c9d8c55000)。  
感谢廖雪峰提供的教程，让我从这个程序中收获良多。

Blog现有2个分支：

1. [awesome](https://github.com/zhu327/boz/tree/awesome)：廖雪峰教程的标准实现
2. master：: 部署在SAE(Sina App Engine)的版本

<!--more-->
master相对与awesome的改变主要是在前端的改变，前端可分为访客面与管理面，两面相对独立。  
访客面UI完全clone自[Heroic Yang's Blog](http://heroicyang.com/)；  
管理面UI由[Bootstrap](https://github.com/twbs/bootstrap/)简单的拼凑出来，界面简陋，实现了Blog后台管理基本功能。

开发环境：  
OSX, Python, MySQL, MySQLdb, Jinja2, misaka

blog设计：

1. 访客面 MVC
2. 管理面 MVVM

blog实现了一个简单的Python Web框架，在www/transwarp目录下，包括对MySQLdb的封装，一个简单的ORM实现，以及一个WSGI的web框架实现。

数据库使用MySQL，模版引擎用到了Jinja2，使用misaka来支持markdown格式。  
前端管理面用到了Bootstrap jQuery 以及MVVM库Vue.js。

部署：

1. MySQL中导入schema.sql
2. 修改config_override.py配置，可参考config_default.py
3. 修改template模版，包括blog名称，about页面信息
4. python wsgiapp.py即可运行，SAE分支还需要修改config.yaml相关信息
5. 后台/manage/默认用户名:admin@example.com 密码:123456，首次部署后需要到/manage/user修改密码

Boz是在业余学习的练习作品，前后学习编码差不多用了1个多月，学习了很多东西，准备输出学习笔记记录在<http://bozpy.sinaapp.com>上，各位看官如有兴趣，请订阅。
