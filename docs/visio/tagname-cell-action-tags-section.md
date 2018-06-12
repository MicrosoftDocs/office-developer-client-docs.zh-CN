---
title: TagName 单元格（“Action Tags”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60088
localization_priority: Normal
ms.assetid: 28d1cd60-4fb6-9feb-1a13-0962798ac1ad
description: 用作将动作标记与其动作相关联的关键字的动作标记的名称。
ms.openlocfilehash: dbac3d4dff9d2ffd18bba75db56cafc08f5e0ee8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781472"
---
# <a name="tagname-cell-action-tags-section"></a>TagName 单元格（“Action Tags”内容）

用作将动作标记与其动作相关联的关键字的动作标记的名称。
  
> [!NOTE]
> 在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。 
  
## <a name="remarks"></a>注释

 在动作标记部分中的 TagName 单元格结合使用，在操作部分，若要将某个动作标记与其动作相关联的 TagName 单元格。 在操作部分中的行还具有 TagName 单元格，并且具有相同的 TagName 单元格值作为此单元格的行定义要为此动作标记执行的操作。 
  
若要获取对 TagName 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 智能标记。  *名称*。TagName 其中智能标记。 *name*是动作标记行的名称  <br/> |
   
若要从某个程序按索引获取对 TagName 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionSmartTag** <br/> |
| 行索引：  <br/> |**visRowSmartTag** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visSmartTagName** <br/> |
   

