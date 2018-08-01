---
title: TxtLocPinX 单元格（“Text Transform”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251275
localization_priority: Normal
ms.assetid: cbfc4e91-10d1-d50e-3e8a-f269f7123276
description: 确定 x-文本块的相对于原点的文本块的旋转中心的坐标。 默认公式为：
ms.openlocfilehash: 6eb48532bb19bce5b0d22ed2cd0997014721df88
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781559"
---
# <a name="txtlocpinx-cell-text-transform-section"></a>TxtLocPinX 单元格（“Text Transform”部分）

确定*x* -文本块的相对于原点的文本块的旋转中心的坐标。 默认公式为： 
  
= TxtWidth \* 0.5
  
该公式计算文本块的水平中心。
  
## <a name="remarks"></a>注释

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 TxtLocPinX 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | TxtLocPinX  <br/> |
   
要从某个程序按索引获取对 TxtLocPinX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowTextXForm** <br/> |
| 单元格索引：  <br/> |**visXFormLocPinX** <br/> |
   

