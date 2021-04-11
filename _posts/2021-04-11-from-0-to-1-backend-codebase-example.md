---
layout: post
title: 从0到1，以一个后端服务为例
categories: [Engineering Practices]
description: 以一个简单的Spring boot的服务为例，介绍从O到1搭建代码库需要使用的工程实践。
keywords: Software Development
---



## 语言和框架选择
- 选择能解决业务场景的合适的语言和框架 如python or java，Spring MVC or Spring Webflux 
- 选择团队成员有足够经验的编程语言
- 选择支持性好的尽可能新的版本

## 依赖管理和构建工具
Maven, Gradle

## 静态代码检查
### 代码风格检查 
checkstyle
### 项目依赖扫描 
oss-index SonaQube 
### 镜像扫描 
Aqua cloud

## 自动化测试
### 单元测试 Junit Jupiter
### API测试 Newman

## CI/CD流水线
CircleCI 
Fast - Cache

## 基础设施即代码
Terraform

## 构建你的第一个API - Health Check API

## 认证和授权

