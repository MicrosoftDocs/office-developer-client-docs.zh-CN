---
title: LockCustProp 单元格（“Protection”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60055
localization_priority: Normal
ms.assetid: d1c23f1d-485d-a897-594d-15d6e8d0fb3c
description: 确定用户是否可以使用“定义形状数据”对话框或“形状数据”窗口的快捷菜单在用户界面 (UI) 中添加、删除或修改形状数据。
ms.openlocfilehash: 001123f3bd08d35f6f8e4874e20f2ee073835494
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359604"
---
# <a name="lockcustprop-cell-protection-section"></a>LockCustProp 单元格（“Protection”内容）

确定用户是否可以使用 **“定义形状数据”** 对话框或 **“形状数据”** 窗口的快捷菜单在用户界面 (UI) 中添加、删除或修改形状数据。 
  
|**Value**|**说明**|
|:-----|:-----|
|TRUE  <br/> |**“形状数据”** 窗口中的快捷菜单上的 **“定义形状数据”** 命令被禁用。  <br/> |
|FALSE  <br/> |**“形状数据”** 窗口中的快捷菜单上的 **“定义形状数据”** 命令被启用（默认值）。  <br/> |
   
## <a name="remarks"></a>注解

值为 TRUE 则表示不禁止用户更改形状数据项的值，或者不禁止用户在 ShapeSheet 窗口中更改“Shape Data”内容。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LockCustProp 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |LockCustProp  <br/> |
   
若要从某个程序按索引获取对 LockCustProp 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowLock** <br/> |
|单元格索引：  <br/> |**visLockCustProp** <br/> |
   

