---
title: YGridSpacing 单元格 ( &amp; "标尺网格" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1210
localization_priority: Normal
ms.assetid: 30766e13-c90d-62fc-9c98-35ad7b0b4056
description: 指定固定网格中垂直线条间的距离 (YGridDensity = 0)。
ms.openlocfilehash: fc355b4e509494e9e7570122a8a3a7a3ce2e0588
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417460"
---
# <a name="ygridspacing-cell-ruler-amp-grid-section"></a>YGridSpacing 单元格 ( &amp; "标尺网格" 部分)

指定固定网格中垂直线条间的距离 (YGridDensity = 0)。
  
## <a name="remarks"></a>说明

对应于 "**标尺&amp;网格**" 对话框 (在 "**视图**" 选项卡上, 单击 "**显示**" 箭头) 中的 "垂直**最小间距**" 选项。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 YGridSpacing 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |YGridSpacing  <br/> |
   
若要从某个程序按索引获取对 YGridSpacing 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowRulerGrid** <br/> |
|单元格索引：  <br/> |**visYGridSpacing** <br/> |
   

