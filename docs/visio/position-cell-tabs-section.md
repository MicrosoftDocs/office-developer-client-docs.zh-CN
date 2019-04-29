---
title: Position 单元格（“Tabs”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251755
localization_priority: Normal
ms.assetid: 40d7e38e-b3b0-8616-ed27-1f963a841e03
description: 指定制表位的位置。制表位位置与绘图比例无关。即使绘图比例进行调整，制表位位置仍然保持不变。
ms.openlocfilehash: ef17b38d708103ca004594ba04ff5b8d1ada13bf
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409928"
---
# <a name="position-cell-tabs-section"></a>Position 单元格（“Tabs”内容）

指定制表位的位置。制表位位置与绘图比例无关。即使绘图比例进行调整，制表位位置仍然保持不变。
  
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Position 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 张.  *ij* *i*和*j* = <1>, 2, 3 .。。  <br/> |
   
要从某个程序按索引获取对 Position 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionTab** <br/> |
| 行索引：  <br/> |**visRowTab** +  *i* = ** 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> | (*j* * 3) + **visTabPos** <br/> |
   

