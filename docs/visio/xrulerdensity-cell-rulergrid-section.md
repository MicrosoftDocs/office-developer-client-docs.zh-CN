---
title: XRulerDensity 单元格 ( &amp; "标尺网格" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1165
localization_priority: Normal
ms.assetid: c11717c5-eb0e-e4fa-5a91-c62ecc048635
description: 指定页面标尺上的水平细分线。
ms.openlocfilehash: f459e5d1d19580201f1404ac2d1ae53c824293f8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331848"
---
# <a name="xrulerdensity-cell-ruler-amp-grid-section"></a>XRulerDensity 单元格 ( &amp; "标尺网格" 部分)

指定页面标尺上的水平细分线。
  
|**Value**|**说明**|**自动常量**|
|:-----|:-----|:-----|
|0  <br/> |Fixed  <br/> |**visRulerFixed** <br/> |
|8 (&amp;H8)  <br/> |粗  <br/> |**visRulerCoarse** <br/> |
|16 (&amp;H10)  <br/> |标准（默认）  <br/> |**visRulerNormal** <br/> |
|32 (&amp;H20)  <br/> |细化  <br/> |**visRulerFine** <br/> |
   
## <a name="remarks"></a>注解

此单元格对应于 "**标尺&amp;网格**" 对话框 (在 "**视图**" 选项卡上, 单击 "**显示**" 箭头) 中的 "水平**细分**线" 选项。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 XRulerDensity 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |XRulerDensity  <br/> |
   
若要从某个程序按索引获取对 XRulerDensity 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowRulerGrid** <br/> |
|单元格索引：  <br/> |**visXRulerDensity** <br/> |
   

