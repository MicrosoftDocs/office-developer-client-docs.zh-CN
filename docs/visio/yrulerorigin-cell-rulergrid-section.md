---
title: YRulerOrigin 单元格 ( &amp; "标尺网格" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1220
localization_priority: Normal
ms.assetid: 5d21b64f-a559-76ef-06df-d24c048cc6ef
description: 指定页面 y 轴标尺上的零点。
ms.openlocfilehash: ead9ca453bfeb86f32a943950b297b9b629de95d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32284963"
---
# <a name="yrulerorigin-cell-ruler-amp-grid-section"></a>YRulerOrigin 单元格 ( &amp; "标尺网格" 部分)

指定页面 y 轴标尺上的零点。
  
## <a name="remarks"></a>注解

此单元格对应于 "**标尺&amp;网格**" 对话框 (在 "**视图**" 选项卡上, 单击 "**显示**" 箭头) 中的 "垂直**标尺零点**" 选项。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 YRulerOrigin 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |YRulerOrigin  <br/> |
   
若要从某个程序按索引获取对 YRulerOrigin 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowRulerGrid** <br/> |
|单元格索引：  <br/> |**visYRulerOrigin** <br/> |
   

