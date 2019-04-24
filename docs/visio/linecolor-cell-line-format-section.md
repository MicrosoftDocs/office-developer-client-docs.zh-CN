---
title: LineColor 单元格（“Line Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm535
localization_priority: Normal
ms.assetid: d857b48b-9a3d-a1e1-5ad2-6816a492c8ab
description: 确定形状的线条颜色。
ms.openlocfilehash: d0b4ebee6d96bc67c9ca45e8a6194cb91ed6c7f5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359302"
---
# <a name="linecolor-cell-line-format-section"></a>LineColor 单元格（“Line Format”内容）

确定形状的线条颜色。
  
## <a name="remarks"></a>注解

若要设置线条颜色，请输入一个介于 0 和 23 之间的数字，该数字是线条颜色集合中的索引。可以在 **“线条”** 对话框中查看线条颜色集合（在 **“开始”** 选项卡上的 **“形状”** 组中，单击 **“线条”**，指向 **“粗细”**，然后单击 **“其他线条”**）。还可以在 **“线条”** 对话框中设置 LineColor 的值。 
  
若要输入自定义颜色，请使用 RGB 或 HSL 函数。 自定义颜色的值是其 RGB 颜色, 而 rgb ( *r, g, b*), 而不是数字, 将显示在 ShapeSheet 窗口中。 在数值运算中使用自定义颜色时，其值将大于或等于 24。 
  
您可以在 LineColorTrans 单元格中设置线条颜色的透明度。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LineColor 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |LineColor  <br/> |
   
若要从某个程序按索引获取对 LineColor 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowLine** <br/> |
|单元格索引：  <br/> |**visLineColor** <br/> |
   

