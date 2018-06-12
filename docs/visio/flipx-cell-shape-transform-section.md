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
ms.openlocfilehash: fc014ff6c5a3650361d6afd478a5858f84fb5c47
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780281"
---
# <a name="flipx-cell-shape-transform-section"></a>FlipX 单元格（“Shape Transform”内容）

指出形状是否已经水平翻转。
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 形状已经水平翻转。  <br/> |
| FALSE  <br/> | 形状尚未水平翻转。  <br/> |
   
## <a name="remarks"></a>注释

要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 FlipX 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | FlipX  <br/> |
   
若要从某个程序按索引获取对 FlipX 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowXFormOut** <br/> |
| 单元格索引：  <br/> |**visXFormFlipX** <br/> |
   

