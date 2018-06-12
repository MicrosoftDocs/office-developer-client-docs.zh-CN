---
title: YGridOrigin 单元格 (标尺&amp;网格部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1205
localization_priority: Normal
ms.assetid: eeec59f8-f301-5639-ffd6-8a36b2bf9c8f
description: 指定网格的垂直起点。
ms.openlocfilehash: 2d914fc15df8a100066ad17a2e35001fe8a4d587
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781709"
---
# <a name="ygridorigin-cell-ruler-amp-grid-section"></a>YGridOrigin 单元格 (标尺&amp;网格部分)

指定网格的垂直起点。
  
## <a name="remarks"></a>注解

此单元格对应于垂直**网格原点**选项中**标尺&amp;网格**对话框 （在**视图**选项卡上，单击**显示**箭头）。 
  
要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 YGridOrigin 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |YGridOrigin  <br/> |
   
若要从某个程序按索引获取对 YGridOrigin 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowRulerGrid** <br/> |
|单元格索引：  <br/> |**visYGridOrigin** <br/> |
   

