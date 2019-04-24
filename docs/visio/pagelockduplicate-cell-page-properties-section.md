---
title: PageLockDuplicate 单元格 ("Page Properties" 内容)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: fbaa7d64-06ef-46d6-81d5-9d7af1c14b65
description: 确定是否可以将页面复制为布尔值。
ms.openlocfilehash: 8ce730fcdc2dff5deac44d8c053b84e82a82d4cb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283662"
---
# <a name="pagelockduplicate-cell-page-properties-section"></a>PageLockDuplicate 单元格 ("Page Properties" 内容)

确定是否可以将页面复制为布尔值。
  
|||
|:-----|:-----|
|TRUE  <br/> |**** 在页面快捷菜单和页面中重复 **。** 已对页面禁用重复的自动化方法。  <br/> |
|FALSE  <br/> |可以复制页面。  <br/> |
   
## <a name="remarks"></a>注解

若要从另一个公式按名称获取对**PageLockDuplicate**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | PageLockDuplicate  <br/> |
   
若要从某个程序按索引获取对**PageLockDuplicate**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPage** <br/> |
| 单元格索引：  <br/> |**visPageLockDuplicate** <br/> |
   

