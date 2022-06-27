---
layout: post
title: 定期的密钥轮换
categories: [Engineering Practices]
description: 介绍密钥轮替的重要性，以及不同场景下密钥轮替的方案和使用到的工具
keywords: Software Development，Secret Rotate
---

背景：介绍几个密钥泄露导致的重大信息泄露事件

## 密钥轮换的好处
* 安全性提升，减少密钥泄露造成的影响
* 确保无需密钥权限的人员无法使用旧密钥
* 降低紧急轮替时系统发生中断的可能性

## 有哪些密钥需要轮替

数据库/ElasticSearch，包含用户名密码，SSL证书等
与API Platform的集成，包含Consumer APP的Secret，Token in Addons等
与Event Platform的集成，包含发布订阅事件使用的Token，消费事件使用的Http Headers认证Token
与其他第三方直接集成，如与Sisense、GoFigure等系统直接API调用使用的用户密码, Sendgrid API Key等
GCP Service Account, AWS Secret Access Key ID


## 密钥的生命周期 ----模式和反模式
* 创建
* 存储
* 轮换
* 销毁


## 工具

* Secret As a Service
  * AWS Secret Manager
  * Google Secret Manager

* Talisman

## 应用程序获取密钥的方式

## 定期自动轮替

## 一些需要注意的事情
* 不同环境使用不同的密钥，先轮换测试环境密钥，再轮换产品环境密钥
* 仔细查看Talisman报错，密钥切勿提交到代码库
* 轮换密钥尽量确保产品无Downtime
* 密钥若需共享给团队成员使用，使用1password并及时更新
* 及时回收无需访问密钥人员的权限
* 自动化轮换密钥


手动VS自动
How
适用场景
前提条件
本地环境
CI配置
监控报警
其他
