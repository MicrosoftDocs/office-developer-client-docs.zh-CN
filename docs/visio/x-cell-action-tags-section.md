---
title: X 单元格（“Action Tags”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60093
localization_priority: Normal
ms.assetid: d13e362b-9b69-30c5-003a-9c5df2aa29f6
description: 形状的本地坐标中放置了动作标记按钮的 x 坐标位置。
ms.openlocfilehash: 9f26bec81563c9813a88ed5c69730266834ee101
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431111"
---
# <a name="x-cell-action-tags-section"></a>X 单元格（“Action Tags”内容）

形状的本地坐标中放置了动作标记按钮的*x*坐标位置。 
  
> [!NOTE]
> 在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。 
  
## <a name="remarks"></a>说明

X 单元格和 Y 单元格定义形状的本地坐标系中的某一点，X Justify 单元格和 Y Justify 单元格定义动作标记按钮相对于该点的放置位置。 
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 X 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> |SmartTags. *名称*。X 其中的智能标记。 *name*是操作标记行的名称  <br/> |
   
要从某个程序按索引获取对 X 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionSmartTag** <br/> |
| 行索引：  <br/> |**visRowSmartTag** +  *i* = ** 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> |**visSmartTagX** <br/> |
   

