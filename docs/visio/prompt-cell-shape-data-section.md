---
title: Prompt 单元格（“Shape Data”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251343
localization_priority: Normal
ms.assetid: 42f42d73-a00c-ca93-adc9-4f8869b9cd42
description: 指定当鼠标悬停在“形状数据”窗口中的某个值上时作为提示出现的说明性文本或指导性文本。
ms.openlocfilehash: 4ecb7eb5a1e775d2f3f5271476ef45cdf020d7c8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405483"
---
# <a name="prompt-cell-shape-data-section"></a>Prompt 单元格（“Shape Data”内容）

指定当鼠标悬停在 **“形状数据”** 窗口中的某个值上时作为提示出现的说明性文本或指导性文本。 
  
## <a name="remarks"></a>备注

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Prompt 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Prop.  *名称*  。提示其中  *Name*  是行名称  <br/> |
   
要从某个程序按索引获取对 Prompt 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionProp** <br/> |
| 行索引：  <br/> |**visRowProp +** *i*  其中  *i*  = 0、1、2...  <br/> |
| 单元格索引：  <br/> |**visCustPropsPrompt** <br/> |
   

