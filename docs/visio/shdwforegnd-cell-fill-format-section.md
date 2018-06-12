---
title: ShdwForegnd 单元格（“Fill Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251244
localization_priority: Normal
ms.assetid: ea153390-631d-79fd-c1ba-4c281239a24e
description: 确定用于形状的投影填充图案的前景（划线）的颜色。
ms.openlocfilehash: f39109a296949d23142017661bb55f0708402d8f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781331"
---
# <a name="shdwforegnd-cell-fill-format-section"></a>ShdwForegnd 单元格（“Fill Format”内容）

确定用于形状的投影填充图案的前景（划线）的颜色。
  
## <a name="remarks"></a>注解

若要设置颜色，请输入 0 到 23 之间的一个数字，该数字是颜色集合中的一个索引。
  
若要输入自定义颜色，使用 RGB 或 HSL 函数。 自定义颜色的值为 RGB 颜色，并且 RGB （ *r、 g、 b*），而不是一个号码，将显示在 ShapeSheet 窗口中。 当使用中的数字运算，自定义颜色具有值将大于或等于，共 24 部分。 
  
您可以在 ShdwForegndTrans 单元格中设置形状的投影填充图案前景色的透明度。
  
要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 ShdwForegnd 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ShdwForegnd  <br/> |
   
若要从某个程序按索引获取对 ShdwForegnd 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowFill** <br/> |
| 单元格索引：  <br/> |**visFillShdwForegnd** <br/> |
   

