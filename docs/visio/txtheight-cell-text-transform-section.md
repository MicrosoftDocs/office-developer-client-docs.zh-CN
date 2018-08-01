---
title: TxtHeight 单元格（“Text Transform”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1025
localization_priority: Normal
ms.assetid: cfa3ecc6-61a8-506c-ba1d-b5e1f757d44f
description: 确定文本块的高度。默认公式为：
ms.openlocfilehash: e9495eef837a61fa9b7ecb2b242fdabc5df30080
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781572"
---
# <a name="txtheight-cell-text-transform-section"></a>TxtHeight 单元格（“Text Transform”部分）

确定文本块的高度。默认公式为：
  
= 高度\*1
  
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 TxtHeight 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | TxtHeight  <br/> |
   
要从某个程序按索引获取对 TxtHeight 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowTextXForm** <br/> |
| 单元格索引：  <br/> |**visXFormHeight** <br/> |
   

