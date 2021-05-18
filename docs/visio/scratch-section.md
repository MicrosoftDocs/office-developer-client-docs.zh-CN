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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411601"
---
# <a name="scratch-section"></a>“Scratch”内容

用于输入和测试可由其他单元格引用的公式的工作区。
  
## <a name="remarks"></a>备注

可以使用 **“插入内容”** 对话框添加此内容。方法是：在 ShapeSheet 窗口中单击右键，然后单击 **“插入内容”**。
  
**Scratch** 部分通常用于隔离重复的复杂计算。 如果您的解决方案具有明确的目的，则为了清楚起见，应更明智的使用 **"User-Defined Cells"** 内容中的单元格，因为可以命名 User 单元格。 
  
**"Scratch"内容中的** 单元格以两种不同的方式使用单位。 X 和 Y 单元格使用绘图单位;A 到 D 单元格不使用单位。  (在 C 程序员的行话中，X 和 Y 单元格为"typed"，单元格 A 到 D 为"void"。) Scratch **X** 和 **Scratch Y** 单元格通常用于派生  *x*  坐标和  *y*  坐标（如 **PinX** 和 **PinY）** 或 **Geometry** 部分单元格中的 X 和 Y 单元格。 Scratch cells A 到 D 可以显示您指定的任何单位。 
  
这些单元格进一步的区别是，它们存储点值的方式不同。 数据中的点Visio x，y 坐标的单个数据包 *( x，y)* 数据包。 当公式返回点值时，将根据公式所在的 ShapeSheet 单元格，以三种方式之一解释该值。 与  *x*  坐标相关的单元格 (例如 **PinX** 或 **Geometry** 内容 X 列中的单元格) 仅提取点值的  *x*  坐标部分。 与  *y*  坐标相关的单元格仅提取点值的  *y*  坐标部分。 
  
例如，Visio三种方法 `PNT(3,4)` 提取公式。 
  
|**Cell**|**输入值**|**Visio 处理方式**|**结果**|
|:-----|:-----|:-----|:-----|
| X  <br/> | `PNT(3,4)` <br/> | `PNTX(PNT(3,4))` <br/> | 3.0000 in.  <br/> |
| Y  <br/> | `PNT(3,4)` <br/> | `PNTY(PNT(3,4))` <br/> | 4.0000 in.  <br/> |
| A-D  <br/> | `PNT(3,4)` <br/> | `PNT(3,4)` <br/> | PNT (3.0000 in.， 4.0000 in.)   <br/> |
   

