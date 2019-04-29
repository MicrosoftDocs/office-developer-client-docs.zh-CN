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
description: 动作标记按钮相对于由 X 单元格和 y 单元格定义的点的 y 轴偏移量。
ms.openlocfilehash: d7a1f5c1feda3624c9f96039e7247c737a91a813
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419980"
---
# <a name="y-justify-cell-action-tags-section"></a>Y Justify 单元格（“Action Tags”内容）

动作标记按钮相对于由 X 单元格和 y 单元格定义的点的*y 轴*偏移量。 
  
> [!NOTE]
> 在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。 
  
|**值**|**说明**|**自动常量**|
|:-----|:-----|:-----|
| 0  <br/> | 靠上对齐（默认值）。  <br/> |**visSmartTagYJustifyTop** <br/> |
| 1  <br/> | 居中。  <br/> |**visSmartTagYJustifyMiddle** <br/> |
| 双面  <br/> | 靠下对齐。  <br/> |**visSmartTagYJustifyBottom** <br/> |
   
## <a name="remarks"></a>说明

x 两端对齐和 y 调整单元格确定操作标记按钮相对于 X 和 Y 单元格定义的点的放置位置。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Y Justify 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | SmartTags.  *名称*。YJustify 其中的智能标记。 *name*是操作标记行的名称  <br/> |
   
要从某个程序按索引获取对 Y Justify 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionSmartTag** <br/> |
| 行索引：  <br/> |**visRowSmartTag** +  *i* = ** 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> |**visSmartTagYJustify** <br/> |
   

