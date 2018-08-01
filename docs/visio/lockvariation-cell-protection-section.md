---
title: LockVariation 单元格（“Protection”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 36acb95d-5d3b-4d8b-9b6c-effbc78c84c2
description: 确定是否应用于形状的页面的主题变体可更改，作为一个布尔值。
ms.openlocfilehash: c3c272a637f28aa4df43f6c23030d6676280138e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780664"
---
# <a name="lockvariation-cell-protection-section"></a>LockVariation 单元格（“Protection”部分）

确定是否应用于形状的页面的主题变体可更改，作为一个布尔值。
  
|||
|:-----|:-----|
|TRUE  <br/> |不能更改应用于页面或形状的当前变体。  <br/> |
|FALSE  <br/> |可以更改的形状的页面变体。  <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**LockVariation**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LockVariation  <br/> |
   
若要从某个程序按索引获取对**LockVariation**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowLock** <br/> |
| 单元格索引：  <br/> |**visLockVariation** <br/> |
   

