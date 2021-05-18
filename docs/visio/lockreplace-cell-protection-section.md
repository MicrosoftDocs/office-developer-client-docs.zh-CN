---
title: 'LockReplace Cell (Protection Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b3880511-dd27-4dc2-9e50-a49084ef8195
description: 指示形状是否可以参与替换操作 (作为目标或替换形状) 。
ms.openlocfilehash: 8b0e3175cacd9b906d91a4185dcd98fad604d8bf
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404139"
---
# <a name="lockreplace-cell-protection-section"></a>LockReplace Cell (Protection Section) 

指示形状是否可以参与替换操作 (作为目标或替换形状) 。 
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |该形状不能替换或用作替换形状。  <br/> 对于画布上的形状，选择形状时，"更改形状"按钮处于禁用状态。  <br/> 对于模具上的形状，单击"更改形状"按钮时，该形状不会显示为替换形状。   <br/> |
|FALSE  <br/> |该形状可以替换或用作替换形状。  <br/> |
   
## <a name="remarks"></a>备注

若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 CellsU 属性从某个程序按名称获取对 **LockReplace** 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LockReplace  <br/> |
   
若要从程序按索引获取对 **LockReplace** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowLock** <br/> |
| 单元格索引：  <br/> |**visLockReplace** <br/> |
   

