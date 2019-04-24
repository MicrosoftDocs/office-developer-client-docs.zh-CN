---
title: NoObjHandles 单元格（“Miscellaneous”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm730
localization_priority: Normal
ms.assetid: 8e1c8c8f-4ed0-0f53-f93f-3a264edc02bd
description: 切换选中形状的选择手柄的显示状态 - 显示或不显示。
ms.openlocfilehash: e46f19d77d1743fb7223b5f7d98f80a05d8f6b07
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357237"
---
# <a name="noobjhandles-cell-miscellaneous-section"></a>NoObjHandles 单元格（“Miscellaneous”内容）

切换选中形状的选择手柄的显示状态 - 显示或不显示。
  
|**Value**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 选中形状后不显示选择手柄。  <br/> |
| FALSE  <br/> | 选中形状后显示选择手柄。  <br/> |
   
## <a name="remarks"></a>注解

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 NoObjHandles 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | NoObjHandles  <br/> |
   
要从某个程序按索引获取对 NoObjHandles 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowMisc** <br/> |
| 单元格索引：  <br/> |**visNoObjHandles** <br/> |
   

