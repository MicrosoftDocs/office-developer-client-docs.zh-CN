---
title: Width 单元格（“Shape Transform”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251194
localization_priority: Normal
ms.assetid: 992ae9d8-ea15-0f5c-ccd6-e4c536099692
description: 包含所选形状的宽度（以绘图单位计）。确定一维形状的宽度的默认公式是：
ms.openlocfilehash: c99f4669f3b27390a5b8e9062d6085a5a9db54e1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415192"
---
# <a name="width-cell-shape-transform-section"></a>Width 单元格（“Shape Transform”内容）

包含所选形状的宽度（以绘图单位计）。确定一维形状的宽度的默认公式是：
  
= SQRT((EndX - BeginX) ^ 2 + (EndY - BeginY) ^ 2)
  
## <a name="remarks"></a>备注

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Width 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Width  <br/> |
   
要从某个程序按索引获取对 Width 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowXFormOut** <br/> |
| 单元格索引：  <br/> |**visXFormWidth** <br/> |
   

