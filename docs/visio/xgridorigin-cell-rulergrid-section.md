---
title: XGridOrigin 单元格 ( &amp; "标尺网格" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1155
localization_priority: Normal
ms.assetid: 2b1a8902-b1d4-c3d9-8c9f-1a28fddacc59
description: 指定网格原点的水平坐标。
ms.openlocfilehash: ee58ea7d950dd7e422f8a60a13bac8aa4ed353a6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322307"
---
# <a name="xgridorigin-cell-ruler-amp-grid-section"></a>XGridOrigin 单元格 ( &amp; "标尺网格" 部分)

指定网格原点的水平坐标。
  
## <a name="remarks"></a>注解

此单元格对应于 "**标尺&amp;网格**" 对话框 (在 "**视图**" 选项卡上, 单击 "**显示**" 箭头) 中的 "水平**网格起点**" 选项。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 XGridOrigin 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |XGridOrigin  <br/> |
   
若要从某个程序按索引获取对 XGridOrigin 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowRulerGrid** <br/> |
|单元格索引：  <br/> |**visXGridOrigin** <br/> |
   

