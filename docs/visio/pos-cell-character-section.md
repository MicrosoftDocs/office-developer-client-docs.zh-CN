---
title: Pos 单元格（“Character”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm805
localization_priority: Normal
ms.assetid: c02186ce-6a20-fbe7-588d-d64c3ea4dec4
description: 确定形状的文本相对于基准线的位置。
ms.openlocfilehash: d5f6823d6f55493095d29054745f62b579a47893
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414016"
---
# <a name="pos-cell-character-section"></a>Pos 单元格（“Character”内容）

确定形状的文本相对于基准线的位置。
  
|**值**|**说明**|**自动常量**|
|:-----|:-----|:-----|
| 0  <br/> | 标准位置  <br/> |**visPosNormal** <br/> |
| 1  <br/> | Superscript  <br/> |**visPosSuper** <br/> |
| 2  <br/> | Subscript  <br/> |**visPosSub** <br/> |
   
## <a name="remarks"></a>备注

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Pos 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Char.Pos[  *i*  ] 其中  *i*  = <1>， 2， 3...  <br/> |
   
要从某个程序按索引获取对 Pos 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionCharacter** <br/> |
| 行索引：  <br/> |**visRowCharacter**  +  *i* 其中 *i* = 0、1、2...  <br/> |
| 单元格索引：  <br/> |**visCharacterPos** <br/> |
   

