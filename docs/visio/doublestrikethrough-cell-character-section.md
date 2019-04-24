---
title: DoubleStrikethrough 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033762
localization_priority: Normal
ms.assetid: c48a77e1-ea3c-7a6d-8c05-f9e0cb434cda
description: 确定文本格式是否设置为带双删除线。
ms.openlocfilehash: d8ef5bdb6e086be9657f51c66c10d578414e1deb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360590"
---
# <a name="doublestrikethrough-cell-character-section"></a>DoubleStrikethrough 单元格（“Character”内容）

确定文本格式是否设置为带双删除线。
  
## <a name="remarks"></a>注解

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 DoubleStrikethrough 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | DoubleStrikethrough [ *i* ] 其中*i* = <1>, 2, 3 .。。  <br/> |
   
要从某个程序按索引获取对 DoubleStrikethrough 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionCharacter** <br/> |
| 行索引：  <br/> |**visRowCharacter** +  *i* = ** 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> |**visCharacterDoubleStrikethrough** <br/> |
   

