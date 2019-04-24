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
ms.openlocfilehash: f45f22001a4d7275bb9367414c8b04ea3c0d9c6e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359988"
---
# <a name="readonly-cell-actions-section"></a>ReadOnly 单元格（“Actions”内容）

控制动作标记菜单或快捷菜单上的动作是否为只读。 
  
> [!NOTE]
> 在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。 
  
|**Value**|**说明**|
|:-----|:-----|
|TRUE  <br/> |动作在菜单上显示，但为只读的。  <br/> |
|FALSE  <br/> |动作在菜单上显示并且可以选择（默认值）。  <br/> |
   
## <a name="remarks"></a>注解

如果显示在动作标记或快捷菜单上的某个动作是只读的，便不能选取它。 它不会灰显而是背景呈彩色，类似标签。 若要使菜单项灰显，请使用 Disabled 单元格。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ReadOnly 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |操作. *名称*。ReadOnlywhere 操作。  *name*是操作行的名称  <br/> |
   
若要从某个程序按索引获取对 ReadOnly 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionAction** <br/> |
|行索引：  <br/> |**visRowAction** +  *i* = ** 0、1、2 .。。  <br/> |
|单元格索引：  <br/> |**visActionReadOnly** <br/> |
   

