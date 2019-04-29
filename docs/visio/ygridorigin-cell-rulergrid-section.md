---
title: YGridOrigin 单元格 ( &amp; "标尺网格" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1205
localization_priority: Normal
ms.assetid: eeec59f8-f301-5639-ffd6-8a36b2bf9c8f
description: 指定网格的垂直起点。
ms.openlocfilehash: fa8ee15d5ef2b5d581a9532336d3983bed17b1dd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404489"
---
# <a name="ygridorigin-cell-ruler-amp-grid-section"></a>YGridOrigin 单元格 ( &amp; "标尺网格" 部分)

指定网格的垂直起点。
  
## <a name="remarks"></a>说明

此单元格对应于 "**标尺&amp;网格**" 对话框 (在 "**视图**" 选项卡上, 单击 "**显示**" 箭头) 中的 "垂直**网格起点**" 选项。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 YGridOrigin 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |YGridOrigin  <br/> |
   
若要从某个程序按索引获取对 YGridOrigin 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowRulerGrid** <br/> |
|单元格索引：  <br/> |**visYGridOrigin** <br/> |
   

