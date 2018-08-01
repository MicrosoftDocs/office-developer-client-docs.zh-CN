---
title: ShapeShdwObliqueAngle 单元格（“Fill Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033174
localization_priority: Normal
ms.assetid: bad4c512-e91f-d459-d65c-a4ab725c3c14
description: 指定形状阴影倾斜方向的角度。
ms.openlocfilehash: 11f172de33dfbb65d0176733f5c0bf8b33db483d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781283"
---
# <a name="shapeshdwobliqueangle-cell-fill-format-section"></a>ShapeShdwObliqueAngle 单元格（“Fill Format”部分）

指定形状阴影倾斜方向的角度。
  
## <a name="remarks"></a>注解

此单元格中的值为零 (0) 时表示角度方向为垂直向上，并且按照顺时针度量。
  
此值对应于 **“阴影”** 对话框（在 **“开始”** 选项卡上的 **“形状”** 组中，单击 **“阴影”**，然后单击 **“阴影选项”**）中的 **“方向”** 设置。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShapeShdwObliqueAngle 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ShapeShdwObliqueAngle  <br/> |
   
若要从某个程序按索引获取对 ShapeShdwObliqueAngle 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowFill** <br/> |
| 单元格索引：  <br/> |**visFillShdwObliqueAngle** <br/> |
   

