---
title: ReplaceLockFormat 单元格 ("更改形状行为" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6973e2e6-7e7f-48ba-95b3-37c959f6ffb1
description: 指示主控形状中指定单元格的值是否覆盖在形状替换操作过程中要替换的形状的值 (包括本地值)。 如果主控形状的 ReplaceLockFormat 单元格设置为 TRUE (1), 则主控形状的格式值将覆盖主控形状替换的形状的所有相应值。
ms.openlocfilehash: 88af22accb7a80640e7553338dae1af48934f246
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427232"
---
# <a name="replacelockformat-cell-change-shape-behavior-section"></a>ReplaceLockFormat 单元格 ("更改形状行为" 部分)

指示主控形状中指定单元格的值是否覆盖在形状替换操作过程中要替换的形状的值 (包括本地值)。 如果主控形状的**ReplaceLockFormat**单元格设置为 TRUE (1), 则主控形状的格式值将覆盖主控形状替换的形状的所有相应值。 
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |如果主控形状的**ReplaceLockFormat**单元格设置为 TRUE, 则主控形状的格式值将覆盖主控形状替换的所有形状的相应值。  <br/> |
|FALSE  <br/> |如果主控形状的**ReplaceLockFormat**单元格设置为 FALSE, 则替换形状包含替换操作后旧形状中的本地格式值。  <br/> |
   
## <a name="remarks"></a>说明

**ReplaceLockFormat**单元格决定在形状替换操作过程中, 主控形状是否会覆盖以下各节中单元格的局部格式值: 
  
- "**填充格式**" 部分 
    
- "**线条格式**" 部分 
    
- "**快速样式**" 部分 
    
- "**主题属性**" 部分 
    
- "**渐变属性**" 部分 
    
- "**棱台属性**" 部分 
    
- "**其他效果属性**" 部分 
    
- "**线条梯度停止点**" 部分 
    
- **填充梯度停止点**部分 
    
若要从另一个公式按名称获取对**ReplaceLockFormat**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ReplaceLockFormat  <br/> |
   
若要从某个程序按索引获取对**ReplaceLockFormat**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowReplaceBehaviors** <br/> |
| 单元格索引：  <br/> |**visReplaceLockFormat** <br/> |
   

