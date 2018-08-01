---
title: LockReplace 单元格（“Protection”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b3880511-dd27-4dc2-9e50-a49084ef8195
description: 指示某个形状是否可以参与替换操作 （作为目标或替换形状中）。
ms.openlocfilehash: 6f3e41d6a6c5b28c55e21961de63d0cc20eeb129
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780630"
---
# <a name="lockreplace-cell-protection-section"></a>LockReplace 单元格（“Protection”部分）

指示某个形状是否可以参与替换操作 （作为目标或替换形状中）。 
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |形状不能取代或用作替换形状。  <br/> 画布上的形状，**更改形状**按钮被禁用时选择形状。  <br/> 模具上形状，该形状不显示为替换形状时单击**更改形状**按钮。  <br/> |
|FALSE  <br/> |形状可以替换或用作替换形状。  <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**LockReplace**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LockReplace  <br/> |
   
若要从某个程序按索引获取对**LockReplace**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowLock** <br/> |
| 单元格索引：  <br/> |**visLockReplace** <br/> |
   

