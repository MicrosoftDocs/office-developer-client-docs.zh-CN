---
title: ReadOnly 单元格（“Actions”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60071
localization_priority: Normal
ms.assetid: 158b4188-570c-3817-bf34-8dc0c64befa5
description: 控制动作标记菜单或快捷菜单上的动作是否为只读。
ms.openlocfilehash: bf2d0f7e50a3126611662af8e068485986c26a13
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781014"
---
# <a name="readonly-cell-actions-section"></a>ReadOnly 单元格（“Actions”部分）

控制动作标记菜单或快捷菜单上的动作是否为只读。 
  
> [!NOTE]
> 在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。 
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |动作在菜单上显示，但为只读的。  <br/> |
|FALSE  <br/> |动作在菜单上显示并且可以选择（默认值）。  <br/> |
   
## <a name="remarks"></a>注解

只读操作时，显示在动作标记菜单或快捷菜单上，但不是能选择它。 它不会灰显，但而不出现在彩色背景，像一个标签上。 若要使变灰该菜单项，请使用 Disabled 单元格。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ReadOnly 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |操作。 *名称*。ReadOnlywhere 操作。  *name*是 Actions 行的名称  <br/> |
   
若要从某个程序按索引获取对 ReadOnly 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionAction** <br/> |
|行索引：  <br/> |**visRowAction** +  *i*其中*i* = 0、 1、 2...  <br/> |
|单元格索引：  <br/> |**visActionReadOnly** <br/> |
   

