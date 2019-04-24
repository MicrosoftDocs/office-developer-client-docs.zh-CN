---
title: NoQuickDrag 单元格（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm80004
localization_priority: Normal
ms.assetid: 8491f459-9de2-8e75-5532-7d3bd0986734
description: 确定当用户单击由 "Geometry" 内容定义的填充区域时, 是否可以选择或拖动形状。
ms.openlocfilehash: d60268685d93ae88abb2840f62b093db1e688c2f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341060"
---
# <a name="noquickdrag-cell-geometry-section"></a>NoQuickDrag 单元格（“Geometry”内容）

确定当用户单击由 "Geometry" 内容定义的填充区域时, 是否可以选择或拖动形状。
  
## <a name="remarks"></a>注解

若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 NoQuickDrag 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |几何图形*i* 。NoQuickDrag, 其中 * i *-<1>, 2, 3 .。。  <br/> |
   
若要从某个程序按索引获取对 NoQuickDrag 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionFirstComponent** +  *i* , 其中*i* = 0, 1, 2 .。。  <br/> |
|行索引：  <br/> |**visRowComponent** <br/> |
|单元格索引：  <br/> |**visCompNoQuickDrag** <br/> |
   

