---
title: Menu 单元格（“Actions”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm690
localization_priority: Normal
ms.assetid: 29af746c-b081-24cf-a30d-a56353ee849e
description: 定义形状或页的快捷菜单或动作标记菜单上显示的菜单项的名称。
ms.openlocfilehash: 195af94c4c36bb3c29a4fadab3c68f8334742952
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780795"
---
# <a name="menu-cell-actions-section"></a>Menu 单元格（“Actions”内容）

定义形状或页的快捷菜单或动作标记菜单上显示的菜单项的名称。 
  
> [!NOTE]
> 在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。 
  
## <a name="remarks"></a>注解

若要在此项之上将分隔符插入菜单，请使用 BeginGroup 单元格。要在菜单底部显示命令，请在命令名之前加百分号字符 (%) 前缀。
  
若要获取对 Menu 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |操作。 *名称*。Menuwhere 操作。  *name*是 Actions 行的名称  <br/> |
   
若要从某个程序按索引获取对 Menu 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionAction** <br/> |
|行索引：  <br/> |**visRowAction** +  *i*其中 i = 0、 1、 2...  <br/> |
|单元格索引：  <br/> |**visActionMenu** <br/> |
   

