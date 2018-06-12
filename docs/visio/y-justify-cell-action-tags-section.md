---
title: Y Justify 单元格（“Action Tags”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1026937
localization_priority: Normal
ms.assetid: 27042b62-7623-95d7-7e10-f589d74605c7
description: Y-偏移量动作标记按钮相对于由 X 和 Y 单元格定义的点。
ms.openlocfilehash: 8f8323d1f392654bf118ece2f78890f2a1b860ec
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781711"
---
# <a name="y-justify-cell-action-tags-section"></a>Y Justify 单元格（“Action Tags”内容）

*Y* -偏移量动作标记按钮相对于由 X 和 Y 单元格定义的点。 
  
> [!NOTE]
> 在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。 
  
|**值**|**说明**|**自动化常量**|
|:-----|:-----|:-----|
| 0  <br/> | 靠上对齐（默认值）。  <br/> |**visSmartTagYJustifyTop** <br/> |
| 1  <br/> | 居中。  <br/> |**visSmartTagYJustifyMiddle** <br/> |
| 2  <br/> | 靠下对齐。  <br/> |**visSmartTagYJustifyBottom** <br/> |
   
## <a name="remarks"></a>备注

X Justify 和 Y Justify 单元格确定动作标记按钮相对于 X 和 Y 单元格中定义的点的放置位置。
  
要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 Y Justify 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 智能标记。  *名称*。YJustify 其中智能标记。 *name*是动作标记行的名称  <br/> |
   
若要从某个程序按索引获取对 Y Justify 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionSmartTag** <br/> |
| 行索引：  <br/> |**visRowSmartTag** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visSmartTagYJustify** <br/> |
   

