---
title: 查看CPU与GPU温度
categories:
  - Linux
tags:
  - Linux
date: 2022-03-24 18:32:08
---

## 查看CPU温度
通 `lm-sensors` 过工具查看：

```sh
# 安装
sudo apt-get install lm-sensors -y
yes | sudo sensors-detect
# 运行
sensors
```

目前我用的这种方式，其他方式可参考：[如何在Ubuntu Linux上获取CPU温度 - 知乎](https://zhuanlan.zhihu.com/p/143123436)

## 查看GPU温度

```bash
nvidia-smi -q -i 0,1 -d TEMPERATURE
```

`-i` 是GPU的序号，从0开始，可指定多个GPU

### 实时监测多GPU温度

```bash
watch -n 0.5 nvidia-smi -q -i 0,1 -d TEMPERATURE
```
