---
title: Visible 单元格（“Layers”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1110
localization_priority: Normal
ms.assetid: 02048012-a814-410b-f26e-56fcfbe106e6
description: 指定属于该图层的形状在绘图页上是否显示出来。
ms.openlocfilehash: 4266debc318c839bdd29fa818d11b5e1da669a9e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357811"
---
# <a name="visible-cell-layers-section"></a>Visible 单元格（“Layers”内容）

指定属于该图层的形状在绘图页上是否显示出来。
  
|**Value**|**说明**|
|:-----|:-----|
|TRUE  <br/> |形状显示出来。  <br/> |
|FALSE  <br/> |形状隐藏起来。  <br/> |
   
## <a name="remarks"></a>注解

此单元格对应于 "**图层属性**" 对话框 (在 "**开始**" 选项卡上的 "**编辑**" 组中, 单击 "**层**", 然后单击 "**图层属性**") 中的 "**可见**" 选项。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Visible 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |"层"。可见 [ *i* ] 其中*i* = <1>, 2, 3 .。。  <br/> |
   
若要从某个程序按索引获取对 Visible 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionLayer** <br/> |
|行索引：  <br/> |**visRowLayer** +  *i* = ** 0、1、2 .。。  <br/> |
|单元格索引：  <br/> |**visLayerVisible** <br/> |
   

