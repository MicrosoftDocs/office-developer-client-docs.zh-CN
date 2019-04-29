---
title: Description 单元格（“Action Tags”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60037
localization_priority: Normal
ms.assetid: feb29b91-0f6e-6353-3dd0-7a280843a517
description: 包含描述动作标记的字符串。当用户将鼠标指针悬停于动作标记上时，此字符串以工具提示的形式显示。
ms.openlocfilehash: 00c7a4c1547927b8d1a979b8ae074f96f26dc17c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415759"
---
# <a name="description-cell-action-tags-section"></a>Description 单元格（“Action Tags”内容）

包含描述动作标记的字符串。当用户将鼠标指针悬停于动作标记上时，此字符串以工具提示的形式显示。
  
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Description 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | SmartTags.  *名称*。智能标记的说明。 *name*是操作标记行的名称  <br/> |
   
要从某个程序按索引获取对 Description 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionSmartTag** <br/> |
| 行索引：  <br/> |**visRowSmartTag** +  *i* = ** 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> |**visSmartTagDescription** <br/> |
   

