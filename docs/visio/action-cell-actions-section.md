---
title: Action 单元格（“Actions”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm5
localization_priority: Normal
ms.assetid: 435e49ee-0b51-8ce3-0589-3f0717026f4a
description: 包含当用户选择快捷菜单或动作标记菜单上的命令时要执行的公式。
ms.openlocfilehash: e6bc576982cad871804cbcbc5f3d9c6bceb558c5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283063"
---
# <a name="action-cell-actions-section"></a>Action 单元格（“Actions”内容）

包含当用户选择快捷菜单或动作标记菜单上的命令时要执行的公式。
  
> [!NOTE]
> 在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。 
  
## <a name="remarks"></a>注解

只有动作发生（而不是输入该公式）后才对 Action 单元格求值。
  
若要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Action 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 操作.  *名称*。操作中的操作。 *name*是操作行的名称  <br/> |
   
要从某个程序按索引获取对 Action 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionAction** <br/> |
| 行索引：  <br/> |**visRowAction** +  *i* = ** 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> |**visActionAction** <br/> |
   

