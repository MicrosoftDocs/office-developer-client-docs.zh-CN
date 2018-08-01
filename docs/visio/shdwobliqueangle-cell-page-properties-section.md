---
title: ShdwObliqueAngle 单元格（“Page Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033178
localization_priority: Normal
ms.assetid: 2e0b9754-3e3b-3a26-4e1a-e09102055c20
description: 包含指定应用默认页面阴影类型时的倾斜方向角度的数字。
ms.openlocfilehash: 4549ce7b5202b4649a925b04ea54c0d5df569599
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781343"
---
# <a name="shdwobliqueangle-cell-page-properties-section"></a>ShdwObliqueAngle 单元格（“Page Properties”部分）

包含指定应用默认页面阴影类型时的倾斜方向角度的数字。
  
## <a name="remarks"></a>注释

此单元格中的值为零 (0) 时表示角度方向为垂直向上，并且按照顺时针度量。
  
 ShapeShdwType 单元格 （页上的形状的阴影类型） 设置为页面默认值 (**visFSTPageDefault** )，以及是倾斜的阴影类型使用此单元格中描述的角度。 ShdwType 单元格中定义的默认页面阴影类型。 
  
要为单个形状设置此行为，请使用“Fill Format”内容中的 ShapeShdwObliqueAngle 单元格。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 ShdwObliqueAngle 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ShdwObliqueAngle  <br/> |
   
要从某个程序按索引获取对 ShdwObliqueAngle 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPage** <br/> |
| 单元格索引：  <br/> |**visPageShdwObliqueAngle** <br/> |
   

