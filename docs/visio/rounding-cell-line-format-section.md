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
ms.openlocfilehash: 0624ec42978292e84965c978d25e4052fc41613f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781132"
---
# <a name="rounding-cell-line-format-section"></a>Rounding 单元格（“Line Format”部分）

指示在路径的两条相邻线段相交处应用的弧形的半径。例如，圆角功能可用于使矩形的四角变为圆角。要设置圆角功能，请输入带度量单位的值（一个数值单位对）。
  
## <a name="remarks"></a>注解

您还可以设置此值在**线条**对话框 （在**主页**选项卡，**形状**组中，单击**线条**，指向**权重**，，然后单击**多行**）。
  
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
   

