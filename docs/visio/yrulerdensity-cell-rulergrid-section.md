---
title: YRulerDensity 单元格（“Ruler &amp; Grid”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1215
localization_priority: Normal
ms.assetid: aebcd321-9d1c-e04e-7c85-3ec1ed851561
description: 指定页面标尺上的垂直细分线。
ms.openlocfilehash: 4b5dcba7a5cb1a588f742b1c2ea6b430cb2af12c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781714"
---
# <a name="yrulerdensity-cell-ruler-amp-grid-section"></a>YRulerDensity 单元格（“Ruler &amp; Grid”部分）

指定页面标尺上的垂直细分线。
  
|**值**|**说明**|**自动常量**|
|:-----|:-----|:-----|
|0  <br/> |固定  <br/> |**visRulerFixed** <br/> |
|8 (&amp;H8)  <br/> |粗糙  <br/> |**visRulerCoarse** <br/> |
|16 (&amp;H10)  <br/> |标准（默认）  <br/> |**visRulerNormal** <br/> |
|32 (&amp;H20)  <br/> |精细  <br/> |**visRulerFine** <br/> |
   
## <a name="remarks"></a>说明

此单元格对应于在垂直**细分线**选项**标尺&amp;网格**对话框 （在**视图**选项卡上，单击**显示**箭头）。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 YRulerDensity 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |YRulerDensity  <br/> |
   
若要从某个程序按索引获取对 YRulerDensity 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowRulerGrid** <br/> |
|单元格索引：  <br/> |**visYRulerDensity** <br/> |
   

