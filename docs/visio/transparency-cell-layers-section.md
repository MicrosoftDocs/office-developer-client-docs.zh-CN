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
ms.openlocfilehash: 7c205612436e7731f268e17c851616beebf809dc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781551"
---
# <a name="transparency-cell-layers-section"></a>Transparency 单元格（“Layers”内容）

确定图层颜色的透明度级别。
  
|**值**|**说明**|
|:-----|:-----|
|0-100  <br/> |表示透明度的百分比。默认值为 0%（完全不透明）。  <br/> |
   
## <a name="remarks"></a>注解

值将四舍五入到最接近半百分比。 值为 100%是完全透明的。 尽管完全透明颜色的图层显示在绘图页上相同为无颜色的图层，它与交互页上的其他对象相同的方式透明度当作 0%。 您还可以通过使用**图层属性**对话框中的滑块控件设置此值 （**主页**选项卡，在**编辑**组中，单击**图层**，，然后单击**图层属性**）。
  
若要获取对 Transparency 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |Layers.ColorTrans [ *i* ] 其中*i* = < 1 >，2，3...  <br/> |
   
若要从某个程序按索引获取对 Transparency 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionLayer** <br/> |
|行索引：  <br/> |**visRowLayer** +  *i*其中*i* = 0、 1、 2...  <br/> |
|单元格索引：  <br/> |**visLayerColorTrans** <br/> |
   

