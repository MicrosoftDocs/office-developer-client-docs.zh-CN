---
title: “Scratch”内容
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm2125
localization_priority: Normal
ms.assetid: 144dd06f-7225-57db-fd19-a58d6bccf0e1
description: 用于输入和测试可由其他单元格引用的公式的工作区。
ms.openlocfilehash: a7d2c6762e96fc19986521c2ba164666b925c928
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344525"
---
# <a name="scratch-section"></a>“Scratch”内容

用于输入和测试可由其他单元格引用的公式的工作区。
  
## <a name="remarks"></a>注解

可以使用 **“插入内容”** 对话框添加此内容。方法是：在 ShapeSheet 窗口中单击右键，然后单击 **“插入内容”**。
  
"**草稿**" 部分通常用于隔离重复的复杂计算。 如果您的解决方案具有明确定义的用途, 则在使用 "**用户定义的单元**格" 部分中的单元格以进行清晰度是 wiser 的, 因为用户单元格可以命名。 
  
"**草稿**" 部分中的单元格以两种不同的方式使用单位。 X 和 Y 单元格使用绘图单位;A 到 D 单元格不使用单位。 (在 C 程序员的术语中, X 和 Y 单元格是 "类型化的", 单元格 A 到 D 是 "void"。)^ **x**和**擦掉 y**单元格通常用于派生*X*和*y*坐标, 如**PinX**和**PinY**, 或在 " **Geometry** " 内容单元格中找到的 x 和 y 单元格。 暂存单元格 A 到 D 可以显示任何指定的单位。 
  
这些单元格进一步的区别是，它们存储点值的方式不同。 Visio 中的一个点是 ( *x, y*) 坐标的单个数据包。 当公式返回点值时，将根据公式所在的 ShapeSheet 单元格，以三种方式之一解释该值。 与*x*坐标相关的单元格 (例如, " **PinX**" 或 " **Geometry** " 内容的 x 列中的单元格) 只提取点值的*x*坐标部分。 与*y*坐标相关的单元格只提取点值的*y*坐标部分。 
  
例如, Visio 以这三种`PNT(3,4)`方式提取公式。 
  
|**Cell**|**输入值**|**Visio 处理方式**|**结果**|
|:-----|:-----|:-----|:-----|
| X  <br/> | `PNT(3,4)` <br/> | `PNTX(PNT(3,4))` <br/> | 3.0000 in.  <br/> |
| Y  <br/> | `PNT(3,4)` <br/> | `PNTY(PNT(3,4))` <br/> | 4.0000 in.  <br/> |
| -D  <br/> | `PNT(3,4)` <br/> | `PNT(3,4)` <br/> | PNT (3.0000, 4.0000)  <br/> |
   

