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
ms.openlocfilehash: 16f0bac8f139c0b03d7826ac377a964d15296dd8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781222"
---
# <a name="scratch-section"></a>“Scratch”部分

用于输入和测试可由其他单元格引用的公式的工作区。
  
## <a name="remarks"></a>注解

可以使用 **“插入内容”** 对话框添加此内容。方法是：在 ShapeSheet 窗口中单击右键，然后单击 **“插入内容”**。
  
**草稿**部分通常用于将隔离重复复杂的计算。 如果您的解决方案必须定义完善的目的，则丝毫因为用户的单元格可以名为**用户定义单元格**部分中为清楚起见使用单元格。 
  
**草稿**部分中的单元格使用两种不同方式的单位。 X 和 Y 单元格使用绘图单位;A 到 D 单元格不使用单位。 （C 程序员术语 X 和 Y 单元格"类型"，并以单元格 A 到 D 是"void。"）**草稿 X**和**Y 草稿**单元格通常用于派生*x*和*y*坐标，如**PinX**和**PinY**或位于**geometry**内容单元格中的 X 和 Y 单元格。 草稿单元格 A 到 D 可以显示任何您指定的单位。 
  
进一步的区别是这些单元格存储点值的方式。 Visio 中的一个点 （ *x，y*） 坐标的单个数据包。 当公式返回点值时，该值被解释中有三种方法，具体取决于公式是在的 ShapeSheet 单元格。 与*x*单元格的坐标 （例如， **PinX**或 X 列中的**geometry**内容中的单元格） 中提取刚刚*x* -协调点值的一部分。 与*y*单元格的坐标提取刚刚*y* -协调点值的一部分。 
  
例如，Visio 提取公式`PNT(3,4)`中以下三种方式。 
  
|**Cell**|**输入值**|**Visio 处理方式**|**结果**|
|:-----|:-----|:-----|:-----|
| X  <br/> | `PNT(3,4)` <br/> | `PNTX(PNT(3,4))` <br/> | 3.0000 in.  <br/> |
| Y  <br/> | `PNT(3,4)` <br/> | `PNTY(PNT(3,4))` <br/> | 4.0000 in.  <br/> |
| A-D  <br/> | `PNT(3,4)` <br/> | `PNT(3,4)` <br/> | PNT (3.0000 英寸，4.0000 中。)  <br/> |
   

