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
ms.openlocfilehash: b6728d44c71f6403e772a6a7e730ba3c18d9eb48
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779893"
---
# <a name="color-cell-layers-section"></a>Color 单元格（“Layers”部分）

指定用于显示图层的颜色。
  
## <a name="remarks"></a>注解

若要设置该颜色，请输入一个介于 0 和 23 之间的数字。
  
此单元格的值对应于**图层属性**对话框中的**图层颜色**设置 （在**主页**选项卡上的**编辑**组中，单击**图层**，然后单击**图层属性**）。
  
若要输入自定义颜色，使用 RGB 或 HSL 函数。 自定义颜色的值为 RGB 颜色，并且 RGB （ *r、 g、 b*），而不是一个号码，将显示在 ShapeSheet 窗口中。 当使用中的数字运算，自定义颜色具有值将大于或等于，共 24 部分。 255 之间的值表示层都有无颜色。 
  
您可以在 Transparency 单元格中设置图层颜色的透明度。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Color 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |Layers.Color [ *i* ] 其中*i* = < 1 >，2，3，...  <br/> |
   
若要从某个程序按索引获取对 Color 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionLayer** <br/> |
|行索引：  <br/> |**visRowLayer** +  *i*其中*i* = 0、 1、 2...  <br/> |
|单元格索引：  <br/> |**visLayerColor** <br/> |
   

