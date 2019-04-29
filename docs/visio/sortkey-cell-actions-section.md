---
title: SortKey 单元格（“Actions”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1027286
localization_priority: Normal
ms.assetid: c0c4b668-f31b-336f-4434-e94a4804ff7c
description: 确定动作在快捷菜单或动作标记菜单上显示的顺序的数字。
ms.openlocfilehash: d4eb98055f199f603003b068dca9fa7b4e377e52
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419658"
---
# <a name="sortkey-cell-actions-section"></a>SortKey 单元格（“Actions”内容）

确定动作在快捷菜单或动作标记菜单上显示的顺序的数字。
  
> [!NOTE]
> 在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。 
  
## <a name="remarks"></a>说明

动作按照从低到高的顺序在动作标记菜单或快捷菜单上显示，最低的数字显示在菜单的顶部。如果两个动作行具有相同的 SortKey 单元格值，则顺序由物理行顺序确定。默认值为 0（零）。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 SortKey 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |操作. *名称*。SortKeywhere 操作。  *name*是操作行的名称  <br/> |
   
若要从某个程序按索引获取对 SortKey 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionAction** <br/> |
|行索引：  <br/> |**visRowAction** +  *i* = ** 0、1、2 .。。  <br/> |
|单元格索引：  <br/> |**visActionSortKey** <br/> |
   

