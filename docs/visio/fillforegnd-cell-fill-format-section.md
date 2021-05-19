---
title: FillForegnd 单元格（“Fill Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251241
localization_priority: Normal
ms.assetid: 7548a480-4dce-45e0-281b-f6f8bdf05c0b
description: 确定用于形状的填充图案的前景（划线）颜色。
ms.openlocfilehash: 352fecf8d99069cfb5ebd72d295284dc03446364
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415563"
---
# <a name="fillforegnd-cell-fill-format-section"></a>FillForegnd 单元格（“Fill Format”内容）

确定用于形状的填充图案的前景（划线）颜色。
  
## <a name="remarks"></a>备注

若要设置该颜色，请输入一个介于 0 和 23 之间的数字。
  
若要输入自定义颜色，请使用 RGB 或 HSL 函数。 自定义颜色的值是它的 RGB 颜色，RGB ( *r、g、b*) 而不是数字将显示在 ShapeSheet 窗口中。 在数值运算中使用自定义颜色时，其值将大于或等于 24。 
  
您可以在 FillForegndTrans 单元格中设置前景填充的透明度。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 FillForegnd 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |FillForegnd  <br/> |
   
若要从某个程序按索引获取对 FillForegnd 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowFill** <br/> |
|单元格索引：  <br/> |**visFillForegnd** <br/> |
   

