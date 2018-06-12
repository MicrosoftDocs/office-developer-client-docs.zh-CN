---
title: TagName 单元格（“Actions”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60087
localization_priority: Normal
ms.assetid: e593e95d-f975-481d-69cd-619049d4427d
description: 包含此动作所关联的动作标记的名称。
ms.openlocfilehash: e1495a34769cbcfdd687491855d1f9c761de2b4e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781488"
---
# <a name="tagname-cell-actions-section"></a>TagName 单元格（“Actions”内容）

包含此动作所关联的动作标记的名称。
  
> [!NOTE]
> 在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。 
  
## <a name="remarks"></a>注解

“Actions”内容中的 TagName 单元格与“Action Tags”内容中的 TagName 单元格结合使用，可以将某个动作标记与其动作相关联。 
  
- 如果 Actions 行中的 TagName 单元格为空，该动作将显示在快捷菜单中，不在动作标记菜单上。
    
- 如果 Actions 行中的 TagName 单元格值与 Smart Tags 行中的 TagName 单元格值匹配，则该动作将显示在动作标记菜单。
    
- 如果该操作的 TagName 单元格包含一个值，但不匹配任何形状标记行中的 TagName 值，该操作未显示在任何动作标记菜单或快捷菜单。
    
- 如果几个智能标记行具有相同的 TagName 值，它们将显示相同的动作。
    
要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 TagName 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |操作。 *名称*。TagNamewhere 操作。  *name*是 Actions 行的名称  <br/> |
   
若要从某个程序按索引获取对 TagName 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionAction** <br/> |
|行索引：  <br/> |**visRowAction** +  *i*其中*i* = 0、 1、 2...  <br/> |
|单元格索引：  <br/> |**visActionTagName** <br/> |
   

