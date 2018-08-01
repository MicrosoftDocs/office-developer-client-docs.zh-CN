---
title: TxtAngle 单元格（“Text Transform”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251272
localization_priority: Normal
ms.assetid: b8482cd8-5205-40ef-b4e1-4ceb197ac80f
description: 确定文本块的当前相对于 x 的旋转角度-轴的形状。 默认值为 0 度。
ms.openlocfilehash: 08ed4422392a355db948fa947abdfd3772dec0a9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781564"
---
# <a name="txtangle-cell-text-transform-section"></a>TxtAngle 单元格（“Text Transform”部分）

确定文本块的当前相对于*x*的旋转角度-轴的形状。 默认值为 0 度。 
  
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 TxtAngle 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | TxtAngle  <br/> |
   
要从某个程序按索引获取对 TxtAngle 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowTextXForm** <br/> |
| 单元格索引：  <br/> |**visXFormAngle** <br/> |
   

