---
title: 'XGridDensity Cell (Ruler &amp; Grid Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1150
localization_priority: Normal
ms.assetid: db7b353f-4379-8865-1c35-36b89cf93257
description: 指定要使用的水平网格的类型。
ms.openlocfilehash: 5ebd172e56a66bfb39bd9bfa20967bb6b52c5aa2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436039"
---
# <a name="xgriddensity-cell-ruler-amp-grid-section"></a>XGridDensity Cell (Ruler &amp; Grid Section) 

指定要使用的水平网格的类型。
  
|**值**|**说明**|**自动常量**|
|:-----|:-----|:-----|
|0  <br/> |Fixed  <br/> |**visGridFixed** <br/> |
|2  <br/> |粗细  <br/> |**visGridCoarse** <br/> |
|4   <br/> |标准（默认）  <br/> |**visGridNormal** <br/> |
|8   <br/> |精细  <br/> |**visGridFine** <br/> |
   
## <a name="remarks"></a>备注

此单元格对应于"视图"选项卡上"标尺网格"对话框中 (网格间距"选项，单击"显示") 。  **&amp;** 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 XGridDensity 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |XGridDensity  <br/> |
   
若要从某个程序按索引获取对 XGridDensity 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowRulerGrid** <br/> |
|单元格索引：  <br/> |**visXGridDensity** <br/> |
   

