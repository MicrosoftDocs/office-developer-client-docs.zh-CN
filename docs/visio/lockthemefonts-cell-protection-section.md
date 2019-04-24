---
title: LockThemeFonts 单元格 ("Protection" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 1ce8b52c-b6c1-4764-b4ec-00c7efb8929d
description: 通过应用新的主题防止更改主题属性行中的 FontIndex 单元格。 不会阻止用户在 ShapeSheet 中手动编辑此值。
ms.openlocfilehash: b3bd21c1dcd8c8c13d843c50cb29edcc5b8c4999
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358091"
---
# <a name="lockthemefonts-cell-protection-section"></a>LockThemeFonts 单元格 ("Protection" 部分)

通过应用新的主题防止更改**主题属性**行中的**FontIndex**单元格。 不会阻止用户在 ShapeSheet 中手动编辑此值。 
  
|**Value**|**说明**|
|:-----|:-----|
|TRUE  <br/> |除非直接在 ShapeSheet 中进行更改, 否则无法更改**FontIndex**单元格的当前值。  <br/> |
|FALSE  <br/> |当主题发生更改时, **FontIndex**单元格可以从其当前值更改。  <br/> |
   
## <a name="remarks"></a>注解

若要从另一个公式按名称获取对**LockThemeFonts**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LockThemeFonts  <br/> |
   
若要从某个程序按索引获取对**LockThemeFonts**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowLock** <br/> |
| 单元格索引：  <br/> |**visLockThemeFonts** <br/> |
   

