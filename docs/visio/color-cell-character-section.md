---
title: Color 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm160
localization_priority: Normal
ms.assetid: 1c9aab2e-6c2f-0684-4e66-c35ac71883d6
description: 确定形状的文本要使用的颜色。
ms.openlocfilehash: a27d957781ca9a784e7ab9d5c1ce4f533b9a55ba
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439987"
---
# <a name="color-cell-character-section"></a>Color 单元格（“Character”内容）

确定形状的文本要使用的颜色。
  
## <a name="remarks"></a>备注

若要设置该颜色，请输入一个介于 0 和 23 之间的数字。
  
若要输入自定义颜色，请使用 RGB 或 HSL 函数。 自定义颜色的值是它的 RGB 颜色，RGB ( *r、g、b*) 而不是数字将显示在 ShapeSheet 窗口中。 在数值运算中使用自定义颜色时，其值将大于或等于 24。 
  
您可以在 Transparency 单元格中设置文本颜色的透明度。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Color 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |Char.Color[ *i*  ] 其中  *i*  = <1>，2， 3， ...  <br/> |
   
若要从某个程序按索引获取对 Color 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionCharacter** <br/> |
|行索引：  <br/> |**visRowCharacter**  +  *i* 其中 *i* = 0， 1， 2， ...  <br/> |
|单元格索引：  <br/> |**visCharacterColor** <br/> |
   

