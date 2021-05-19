---
title: FlipX 单元格（“Shape Transform”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251197
localization_priority: Normal
ms.assetid: 8d4f5e14-4f17-05a6-4092-5a102c9dc85f
description: 指出形状是否已经水平翻转。
ms.openlocfilehash: b7a4a15e5a7759eddcda3ec391a81f14df545691
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415948"
---
# <a name="flipx-cell-shape-transform-section"></a>FlipX 单元格（“Shape Transform”内容）

指出形状是否已经水平翻转。
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 形状已经水平翻转。  <br/> |
| FALSE  <br/> | 形状尚未水平翻转。  <br/> |
   
## <a name="remarks"></a>备注

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 FlipX 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | FlipX  <br/> |
   
要从某个程序按索引获取对 FlipX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowXFormOut** <br/> |
| 单元格索引：  <br/> |**visXFormFlipX** <br/> |
   

