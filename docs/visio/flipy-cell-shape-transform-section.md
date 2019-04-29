---
title: FlipY 单元格（“Shape Transform”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251198
localization_priority: Normal
ms.assetid: 062022ff-e243-2540-becd-d9b969ce83ce
description: 指出形状是否已经垂直翻转。
ms.openlocfilehash: 44ea0341cda3655e8acc69e82e89acddac69b80d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417446"
---
# <a name="flipy-cell-shape-transform-section"></a>FlipY 单元格（“Shape Transform”内容）

指出形状是否已经垂直翻转。
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 形状已经垂直翻转。  <br/> |
| FALSE  <br/> | 形状尚未垂直翻转。  <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 FlipY 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | FlipY  <br/> |
   
要从某个程序按索引获取对 FlipY 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowXFormOut** <br/> |
| 单元格索引：  <br/> |**visXFormFlipY** <br/> |
   

