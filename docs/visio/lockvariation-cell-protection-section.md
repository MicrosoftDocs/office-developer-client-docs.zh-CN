---
title: LockVariation 单元格 ("Protection" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 36acb95d-5d3b-4d8b-9b6c-effbc78c84c2
description: 确定应用于页面或形状的主题变体是否可更改为布尔值。
ms.openlocfilehash: 69c991e3da7a96d6c59dc825dfb78fdad3d432e7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427925"
---
# <a name="lockvariation-cell-protection-section"></a>LockVariation 单元格 ("Protection" 部分)

确定应用于页面或形状的主题变体是否可更改为布尔值。
  
|||
|:-----|:-----|
|TRUE  <br/> |应用于页面或形状的当前变体无法更改。  <br/> |
|FALSE  <br/> |可以更改页面或形状的变体。  <br/> |
   
## <a name="remarks"></a>说明

若要从另一个公式按名称获取对**LockVariation**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LockVariation  <br/> |
   
若要从某个程序按索引获取对**LockVariation**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowLock** <br/> |
| 单元格索引：  <br/> |**visLockVariation** <br/> |
   

