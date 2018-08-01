---
title: LockThemeIndex 单元格（“Protection”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7b781727-267b-4589-ab40-cfc79bb96c2d
description: 防止被更改通过应用新主题，或选择新连接器方案 ThemeIndex 主题属性行中的单元格。 不阻止用户手动编辑 ShapeSheet 中的此值。
ms.openlocfilehash: 4bef3eb799c943ff89027e69ae8580c9c0e51243
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780650"
---
# <a name="lockthemeindex-cell-protection-section"></a>LockThemeIndex 单元格（“Protection”部分）

防止被更改通过应用新主题，或选择新连接器方案**ThemeIndex** **主题属性**行中的单元格。 不阻止用户手动编辑 ShapeSheet 中的此值。 
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |无法从其当前值更改**ThemeIndex**单元格，除非直接 ShapeSheet 中的更改。  <br/> |
|FALSE  <br/> |主题发生更改时，可以从其当前值更改**ThemeIndex**单元格。  <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**LockThemeIndex**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LockThemeIndex  <br/> |
   
若要从某个程序按索引获取对**LockThemeIndex**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowLock** <br/> |
| 单元格索引：  <br/> |**visLockThemeIndex** <br/> |
   

