---
title: ReplaceLockText 单元格 ("更改形状行为" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 31f43ebe-3758-4fd9-83b5-775041c5890f
description: 指示主控形状中指定单元格的值是否覆盖在形状替换操作过程中要替换的形状的值 (包括本地值)。 ReplaceLockText 确定主控形状上显示的文本是否覆盖正在替换的形状的文本。
ms.openlocfilehash: 299bd571ad935886879abb11108c3d0bd28e3183
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348200"
---
# <a name="replacelocktext-cell-change-shape-behavior-section"></a>ReplaceLockText 单元格 ("更改形状行为" 部分)

指示主控形状中指定单元格的值是否覆盖在形状替换操作过程中要替换的形状的值 (包括本地值)。 **ReplaceLockText**确定主控形状上显示的文本是否覆盖正在替换的形状的文本。 
  
|**Value**|**说明**|
|:-----|:-----|
|TRUE  <br/> | 主控形状上的文本将覆盖旧形状上的文本。 此外, 主控形状替换操作过程中, 主控形状将覆盖以下各节中的单元格的值:  <br/> "**文本字段**" 部分  <br/> "**文本块格式**" 部分  <br/> |
|FALSE  <br/> |替换形状包含旧形状中已添加到形状中的任何文本、文本字段或其他文本属性。  <br/> 当替换形状包含旧形状中的文本属性时, 如果旧形状的**字符**和**段落**部分中有多行, 则替换形状也具有这些值。  <br/> |
   
如果设置为 TRUE (1), 则形状主控形状的值将替换要替换的形状上的以下值:
  
- [TheText Cell (Events Section)](thetext-cell-events-section.md)
    
- "字符"[部分](character-section.md)中的单元格
    
- "段落"[部分](paragraph-section.md)中的单元格
    
- "[选项卡" 部分](tabs-section.md)中的单元格
    
## <a name="remarks"></a>注解

若要从另一个公式按名称获取对**ReplaceLockText**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ReplaceLockText  <br/> |
   
若要从某个程序按索引获取对**ReplaceLockText**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowReplaceBehaviors** <br/> |
| 单元格索引：  <br/> |**visReplaceLockText** <br/> |
   

