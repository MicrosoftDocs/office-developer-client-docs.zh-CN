---
title: Rounding 单元格（“Line Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm860
localization_priority: Normal
ms.assetid: c44457ca-997a-5315-44dd-4218e4203550
description: 指示在路径的两条相邻线段相交处应用的弧形的半径。例如，圆角功能可用于使矩形的四角变为圆角。要设置圆角功能，请输入带度量单位的值（一个数值单位对）。
ms.openlocfilehash: d64d3266e3dd2b0a3998955efe271aab04905fbf
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358580"
---
# <a name="rounding-cell-line-format-section"></a>Rounding 单元格（“Line Format”内容）

指示在路径的两条相邻线段相交处应用的弧形的半径。例如，圆角功能可用于使矩形的四角变为圆角。要设置圆角功能，请输入带度量单位的值（一个数值单位对）。
  
## <a name="remarks"></a>注解

您还可以在 "**线条**" 对话框 (在 "**开始**" 选项卡上的 "**形状**" 组中, 单击 "**线条**", 指向 "**粗细**", 然后单击 "**其他线条**") 中设置此值。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Rounding 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |Rounding  <br/> |
   
若要从某个程序按索引获取对 Rounding 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowLine** <br/> |
|单元格索引：  <br/> |**visLineRounding** <br/> |
   

