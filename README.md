# random-image

[TOC]

## 概述

对教程《[Docker系列 WordPress系列 自建随机图API之静态壁纸 - Bensz](https://blognas.hwb0307.com/linux/docker/1363)》中的个人博客随机图API进行Docker化，使其布署更加方便。特性：

+ 基于PHP
+ 依据访问设备类型（PC/iPad vs. Mobile）选择不同壁纸

![](https://chevereto.hwb0307.com/images/2024/05/28/msedge_Lob04vv27a.webp)

## 用法

+ 克隆本仓库

```shell
git clone https://github.com/huangwb8/random-image.git
```

+ 新建镜像`random-image`

```shell
docker build -t random-image .
```

+ 自定义`img.txt`和`img_mobile.txt`
  + `img.txt`是PC端壁纸的URL集合，`img_mobile.txt`是手机端壁纸的URL集合
  + 通过在URL前面添加`#`可沉默该URL，即不进入随机选择
+ 通过docker-compose布署

```shell
docker-compose up -d
```

## 注意

+ 普通用户可按需修改`img.txt`、`img_mobile.txt`和`docker-compose.yml`
+ 高级用户可按需修改`index.php`
