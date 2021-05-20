---
title: 'XGridSpacing Cell (Ruler &amp; Grid Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1160
localization_priority: Normal
ms.assetid: e07dd983-7588-6317-944c-46da2bb65b31
description: 指定固定网格中水平线条间的距离 (XGridDensity = 0)。
ms.openlocfilehash: 05b68a9721dbfc9c03402d384d976c42ef05b134
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435073"
---
# <a name="xgridspacing-cell-ruler-amp-grid-section"></a>XGridSpacing Cell (Ruler &amp; Grid Section) 

指定固定网格中水平线条间的距离 (XGridDensity = 0)。
  
## <a name="remarks"></a>备注

此单元格对应于"视图"选项卡上"标尺网格"对话框中 ("最小间距"选项，单击"显示") 。 **&amp;**  
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 XGridSpacing 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |XGridSpacing  <br/> |
   
若要从某个程序按索引获取对 XGridSpacing 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowRulerGrid** <br/> |
|单元格索引：  <br/> |**visXGridSpacing** <br/> |
   

