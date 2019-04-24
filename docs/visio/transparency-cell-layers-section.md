---
title: Transparency 单元格（“Layers”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm50130
localization_priority: Normal
ms.assetid: 7382e2aa-5e18-19d2-88d8-c4a19a385106
description: 确定图层颜色的透明度级别。
ms.openlocfilehash: fe0aacf167b2400ca10e22a70c9086429f6059f3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280950"
---
# <a name="transparency-cell-layers-section"></a>Transparency 单元格（“Layers”内容）

确定图层颜色的透明度级别。
  
|**Value**|**说明**|
|:-----|:-----|
|0 - 100  <br/> |表示透明度的百分比。默认值为 0%（完全不透明）。  <br/> |
   
## <a name="remarks"></a>注解

这些值被四舍五入为最接近的 0.5 个百分点。值 100% 是完全透明。虽然颜色完全透明的图层在绘图页上看起来和没有颜色的图层相同，但是它与该页上其他对象的交互方式和透明度为 0% 的形状相同。您还可以使用 **“图层属性”** 对话框（在 **“开始”** 选项卡上的 **“编辑”** 组中，单击 **“图层”**，然后单击 **“图层属性”**）中的滑块控件设置此值。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Transparency 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |ColorTrans [ *i* ] 其中*i* = <1>, 2, 3 .。。  <br/> |
   
若要从某个程序按索引获取对 Transparency 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionLayer** <br/> |
|行索引：  <br/> |**visRowLayer** +  *i* = ** 0、1、2 .。。  <br/> |
|单元格索引：  <br/> |**visLayerColorTrans** <br/> |
   

