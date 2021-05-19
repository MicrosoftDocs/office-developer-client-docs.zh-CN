---
title: Color 单元格（“Layers”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm165
localization_priority: Normal
ms.assetid: 61c19342-46fb-48d4-6375-c9ea8306286d
description: 指定用于显示图层的颜色。
ms.openlocfilehash: a2eef24187165cabfdfc8dee49747a2381562d3e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435129"
---
# <a name="color-cell-layers-section"></a>Color 单元格（“Layers”内容）

指定用于显示图层的颜色。
  
## <a name="remarks"></a>备注

若要设置该颜色，请输入一个介于 0 和 23 之间的数字。
  
此单元格值对应于"开始"选项卡上"编辑 ("组中"图层属性"对话框中的"图层颜色"设置，单击"图层"，然后单击"图层属性") 。 
  
若要输入自定义颜色，请使用 RGB 或 HSL 函数。 自定义颜色的值是它的 RGB 颜色，RGB ( *r、g、b*) 而不是数字将显示在 ShapeSheet 窗口中。 在数值运算中使用自定义颜色时，其值将大于或等于 24。 如果值是 255，则指示图层没有颜色。 
  
您可以在 Transparency 单元格中设置图层颜色的透明度。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Color 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |Layers.Color[ *i*  ] 其中  *i*  = <1>，2， 3， ...  <br/> |
   
若要从某个程序按索引获取对 Color 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionLayer** <br/> |
|行索引：  <br/> |**visRowLayer**  +  *i* 其中 *i* = 0， 1， 2， ...  <br/> |
|单元格索引：  <br/> |**visLayerColor** <br/> |
   

