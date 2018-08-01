---
title: YGridDensity 单元格（“Ruler &amp; Grid”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251363
localization_priority: Normal
ms.assetid: 3ea2b3c7-0c69-a9f2-379f-8daa0c665810
description: 指定要使用的垂直网格的类型。
ms.openlocfilehash: 4e0d1b1dc6f3da95b9328342e0398313b6c85eb4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781716"
---
# <a name="ygriddensity-cell-ruler-amp-grid-section"></a>YGridDensity 单元格（“Ruler &amp; Grid”部分）

指定要使用的垂直网格的类型。
  
|**值**|**说明**|**自动常量**|
|:-----|:-----|:-----|
|0  <br/> |固定  <br/> |**visGridFixed** <br/> |
|2  <br/> |粗糙  <br/> |**visGridCoarse** <br/> |
|4  <br/> |标准（默认）  <br/> |**visGridNormal** <br/> |
|8  <br/> |精细  <br/> |**visGridFine** <br/> |
   
## <a name="remarks"></a>说明

此单元格对应于垂直**网格间距**选项中**标尺&amp;网格**对话框 （在**视图**选项卡上，单击**显示**箭头）。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 YGridDensity 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |YGridDensity  <br/> |
   
若要从某个程序按索引获取对 YGridDensity 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowRulerGrid** <br/> |
|单元格索引：  <br/> |**visYGridDensity** <br/> |
   

