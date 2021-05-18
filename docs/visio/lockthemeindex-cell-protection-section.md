---
title: 'LockThemeIndex Cell (Protection Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7b781727-267b-4589-ab40-cfc79bb96c2d
description: 通过应用新主题或选择新连接线方案来阻止更改"主题属性"行中的 ThemeIndex 单元格。 不会阻止用户在 ShapeSheet 中手动编辑此值。
ms.openlocfilehash: 519c17f6e00c9aad2b5522bc66b41c0ceb75911b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411237"
---
# <a name="lockthemeindex-cell-protection-section"></a>LockThemeIndex Cell (Protection Section) 

通过应用新主题或选择新连接线方案来阻止更改"主题属性"行中的 **ThemeIndex** 单元格。 不会阻止用户在 ShapeSheet 中手动编辑此值。 
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |**ThemeIndex** 单元格不能更改其当前值，除非直接在 ShapeSheet 中进行更改。  <br/> |
|FALSE  <br/> |主题 **更改时，ThemeIndex** 单元格可以从其当前值更改。  <br/> |
   
## <a name="remarks"></a>备注

若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 CellsU 属性从某个程序按名称获取对 **LockThemeIndex** 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LockThemeIndex  <br/> |
   
若要从程序按索引获取对 **LockThemeIndex** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowLock** <br/> |
| 单元格索引：  <br/> |**visLockThemeIndex** <br/> |
   

