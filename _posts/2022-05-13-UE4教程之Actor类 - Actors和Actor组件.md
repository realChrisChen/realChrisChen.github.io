---
layout: post
toc: true
title: "UE4教程之Actor类 - Actors和Actor组件"
categories: Code
tags: [UE4]
author:
  - Chris Chen
---

### 1. 分类文件夹
<img src = "https://i.postimg.cc/VNyTCMh5/2022-05-13-233346.jpg">

在C++ Classes文件夹的子文件夹FirstProject中，我们创建了衍生自Actor类的Main Character,衍生自Object类的MyObject，同时  
我们也从这些类中创建了Blueprint class，这些BP类是放在Content文件夹中的，所以我们需要将其进行整理. 在Content文件夹中新建一个  
Blueprints文件夹，将MyActor和MyObject_BP移动至Blueprints文件夹中

### 2. 自定义C++类

创建一个可以自定义的Actor类Floater并将其置于MyProject中的GameplayActors文件夹中
 