---
title: XRulerOrigin 单元格 ( &amp; "标尺网格" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1170
localization_priority: Normal
ms.assetid: 328f8ab5-217f-0336-0d56-611eff509fe8
description: 指定页面 x 轴标尺上的零点。
ms.openlocfilehash: d66fd324718ec46b1209c4726eeb2d27c21db8b0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435325"
---
# <a name="xrulerorigin-cell-ruler-amp-grid-section"></a>XRulerOrigin 单元格 ( &amp; "标尺网格" 部分)

指定页面 x 轴标尺上的零点。
  
## <a name="remarks"></a>说明

此单元格对应于 "**标尺&amp;网格**" 对话框 (在 "**视图**" 选项卡上, 单击 "**显示**" 箭头) 中的 "水平**标尺零点**" 选项。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 XRulerOrigin 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |XRulerOrigin  <br/> |
   
若要从某个程序按索引获取对 XRulerOrigin 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowRulerGrid** <br/> |
|单元格索引：  <br/> |**visXRulerOrigin** <br/> |
   

