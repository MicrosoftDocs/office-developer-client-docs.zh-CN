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
ms.openlocfilehash: 823b8db4dc6afe94a5fdac1f62aaa48d7e1b0d80
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404797"
---
# <a name="dynfeedback-cell-miscellaneous-section"></a>DynFeedback 单元格（“Miscellaneous”内容）

更改当用户拖动连接线时所感受到的视觉反馈类型。松开鼠标按钮后，相应而生的连接线形状并不受此设置的影响。此设置不应用于可穿绕的连接线。
  
|**值**|**说明**|**自动常量**|
|:-----|:-----|:-----|
| 0  <br/> | 保持直线（无引线）。  <br/> |**visDynFBDefault** <br/> |
| 1  <br/> | 拖动时显示三条引线。  <br/> |**visDynFBUCon3Leg** <br/> |
| 2  <br/> | 拖动时显示五条引线。  <br/> |**visDynFBUCon5Leg** <br/> |
   
## <a name="remarks"></a>备注

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
   

