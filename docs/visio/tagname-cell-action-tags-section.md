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
ms.openlocfilehash: 777d6c1098888c9835c1ad367bb70926b835180b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417908"
---
# <a name="tagname-cell-action-tags-section"></a>TagName 单元格（“Action Tags”内容）

用作将动作标记与其动作相关联的关键字的动作标记的名称。
  
> [!NOTE]
> 在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。 
  
## <a name="remarks"></a>说明

 “Action Tags”内容中的 TagName 单元格与“Actions”内容中的 TagName 单元格结合使用，可以将某个动作标记与其动作相关联。 "操作" 部分中的行还具有 tagname 单元格, 并且这些具有与此单元格相同的 tagname 单元格值的行定义要对此操作标记执行的操作。 
  
若要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 TagName 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | SmartTags.  *名称*。智能标记所在的 TagName。 *name*是操作标记行的名称  <br/> |
   
要从某个程序按索引获取对 TagName 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionSmartTag** <br/> |
| 行索引：  <br/> |**visRowSmartTag** +  *i* = ** 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> |**visSmartTagName** <br/> |
   

