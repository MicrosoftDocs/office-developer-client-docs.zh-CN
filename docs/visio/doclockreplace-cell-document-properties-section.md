---
title: DocLockReplace 单元格（“Document Properties”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 74eae5e5-80ab-4e10-b292-e58a6d7607d2
description: 确定是否应为此文档禁用用户界面的替换形状。
ms.openlocfilehash: 41552ddad4e48680960c45869ded5cf4f80d760f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780140"
---
# <a name="doclockreplace-cell-document-properties-section"></a>DocLockReplace 单元格（“Document Properties”部分）

确定是否应为此文档禁用用户界面的替换形状。 
  
|||
|:-----|:-----|
|TRUE  <br/> |为灰显状态**替换形状**按钮，在 UI 中。  <br/> |
|FALSE  <br/> |**替换形状**按钮处于活动状态的用户界面中。 用户可以使用本文档中的替换形状功能。  <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**DocLockReplace**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | DocLocReplace  <br/> |
   
若要从某个程序按索引获取对**DocLocReplace**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowDoc** <br/> |
| 单元格索引：  <br/> |* * visDocLockReplace * * <br/> |
   

