---
title: LockThemeFonts 单元格（“Protection”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 1ce8b52c-b6c1-4764-b4ec-00c7efb8929d
description: 防止 FontIndex 行的单元格中主题属性被更改通过应用新主题。 不阻止用户手动编辑 ShapeSheet 中的此值。
ms.openlocfilehash: b90ffe4c5555df017bb0506a78351514c954ec39
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780668"
---
# <a name="lockthemefonts-cell-protection-section"></a>LockThemeFonts 单元格（“Protection”部分）

防止**FontIndex**行的单元格中**主题属性**被更改通过应用新主题。 不阻止用户手动编辑 ShapeSheet 中的此值。 
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |无法从其当前值更改**FontIndex**单元格，除非直接 ShapeSheet 中的更改。  <br/> |
|FALSE  <br/> |主题发生更改时，可以从其当前值更改**FontIndex**单元格。  <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**LockThemeFonts**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LockThemeFonts  <br/> |
   
若要从某个程序按索引获取对**LockThemeFonts**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowLock** <br/> |
| 单元格索引：  <br/> |**visLockThemeFonts** <br/> |
   

