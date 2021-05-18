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
ms.openlocfilehash: 602df83dcb88d4137b0609f9a8b1084a40148a10
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422248"
---
# <a name="shdwforegnd-cell-fill-format-section"></a>ShdwForegnd 单元格（“Fill Format”内容）

确定用于形状的投影填充图案的前景（划线）的颜色。
  
## <a name="remarks"></a>备注

若要设置颜色，请输入 0 到 23 之间的一个数字，该数字是颜色集合中的一个索引。
  
若要输入自定义颜色，请使用 RGB 或 HSL 函数。 自定义颜色的值是它的 RGB 颜色，RGB ( *r、g、b*) 而不是数字将显示在 ShapeSheet 窗口中。 在数值运算中使用自定义颜色时，其值将大于或等于 24。 
  
您可以在 ShdwForegndTrans 单元格中设置形状的投影填充图案前景色的透明度。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShdwForegnd 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ShdwForegnd  <br/> |
   
若要从某个程序按索引获取对 ShdwForegnd 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowFill** <br/> |
| 单元格索引：  <br/> |**visFillShdwForegnd** <br/> |
   

