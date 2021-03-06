---
title: 'YRulerDensity Cell (Ruler &amp; Grid Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1215
localization_priority: Normal
ms.assetid: aebcd321-9d1c-e04e-7c85-3ec1ed851561
description: 指定页面标尺上的垂直细分线。
ms.openlocfilehash: c92c48f6c86fc794cf6f53a87fdb99e67a73b9f5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406799"
---
# <a name="yrulerdensity-cell-ruler-amp-grid-section"></a>YRulerDensity Cell (Ruler &amp; Grid Section) 

指定页面标尺上的垂直细分线。
  
|**值**|**说明**|**自动常量**|
|:-----|:-----|:-----|
|0  <br/> |Fixed  <br/> |**visRulerFixed** <br/> |
|8 (&amp; H8)   <br/> |粗细  <br/> |**visRulerCoarse** <br/> |
|16 (&amp;H10)  <br/> |标准（默认）  <br/> |**visRulerNormal** <br/> |
|32 (&amp;H20)  <br/> |精细  <br/> |**visRulerFine** <br/> |
   
## <a name="remarks"></a>备注

此单元格对应于"视图"选项卡上"标尺网格"对话框中 **("细分线**"选项，单击"显示") 。 **&amp;**  
  
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
   

