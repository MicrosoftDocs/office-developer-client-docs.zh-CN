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
description: 确定用户是否可以添加、 删除或修改用户界面 (UI) 中的形状数据的形状数据窗口中使用定义形状数据对话框或快捷菜单。
ms.openlocfilehash: a88da9e4973f819b398b5bdeda434ede14640797
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780621"
---
# <a name="lockcustprop-cell-protection-section"></a>LockCustProp 单元格（“Protection”内容）

确定用户是否可以添加、 删除或修改用户界面 (UI) 中的形状数据的**形状数据**窗口中使用**定义形状数据**对话框或快捷菜单。 
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |在**形状数据**窗口中的快捷菜单上的**定义形状数据**命令被禁用。  <br/> |
|FALSE  <br/> |启用**形状数据**窗口中的快捷菜单上的**定义形状数据**命令 （默认）。  <br/> |
   
## <a name="remarks"></a>注解

值为 TRUE 则表示不禁止用户更改形状数据项的值，或者不禁止用户在 ShapeSheet 窗口中更改“Shape Data”内容。 
  
要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 LockCustProp 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |LockCustProp  <br/> |
   
若要从某个程序按索引获取对 LockCustProp 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowLock** <br/> |
|单元格索引：  <br/> |**visLockCustProp** <br/> |
   

