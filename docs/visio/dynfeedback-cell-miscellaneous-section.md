---
title: DynFeedback 单元格（“Miscellaneous”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251317
localization_priority: Normal
ms.assetid: 44017319-7146-3431-e476-fbb1a40341ca
description: 更改当用户拖动连接线时所感受到的视觉反馈类型。松开鼠标按钮后，相应而生的连接线形状并不受此设置的影响。此设置不应用于可穿绕的连接线。
ms.openlocfilehash: 858d98c8ee55eb49f58bbe98491ddc8752e75504
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780167"
---
# <a name="dynfeedback-cell-miscellaneous-section"></a>DynFeedback 单元格（“Miscellaneous”部分）

更改当用户拖动连接线时所感受到的视觉反馈类型。松开鼠标按钮后，相应而生的连接线形状并不受此设置的影响。此设置不应用于可穿绕的连接线。
  
|**值**|**说明**|**自动常量**|
|:-----|:-----|:-----|
| 0  <br/> | 保持直线（无引线）。  <br/> |**visDynFBDefault** <br/> |
| 1  <br/> | 拖动时显示三条引线。  <br/> |**visDynFBUCon3Leg** <br/> |
| 2  <br/> | 拖动时显示五条引线。  <br/> |**visDynFBUCon5Leg** <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 DynFeedback 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | DynFeedback  <br/> |
   
要从某个程序按索引获取对 DynFeedback 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowMisc** <br/> |
| 单元格索引：  <br/> |**visDynFeedback** <br/> |
   

