---
title: ReplaceLockText 单元格（“Change Shape Behavior”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 31f43ebe-3758-4fd9-83b5-775041c5890f
description: 指示在主控形状中的指定单元格的值是否覆盖形状替换操作期间要替换的形状 （包括本地值） 的值。 ReplaceLockText 确定是否显示母版上的文本将覆盖要替换的形状的文本。
ms.openlocfilehash: 75fb0831e7361345f04d7912eb0a55959d9417cd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781104"
---
# <a name="replacelocktext-cell-change-shape-behavior-section"></a>ReplaceLockText 单元格（“Change Shape Behavior”部分）

指示在主控形状中的指定单元格的值是否覆盖形状替换操作期间要替换的形状 （包括本地值） 的值。 **ReplaceLockText**确定是否显示母版上的文本将覆盖要替换的形状的文本。 
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> | 主控形状上的文本将覆盖旧形状上的文本。 此外，主控形状的形状替换操作期间覆盖以下各节中的单元格的值：  <br/> **文本域**部分  <br/> **文本块格式**部分  <br/> |
|FALSE  <br/> |替代形状包含任何文本、 文本域或从旧形状其他已添加到形状的文本属性。  <br/> 替代形状包含文本的旧的形状的属性，替换形状也值从旧的形状的**字符**和**段落**部分，如果有拥有多个行。  <br/> |
   
如果设置为 TRUE (1)，该形状的主控形状的值替换为以下要替换的形状上的值：
  
- [TheText Cell (Events Section)](thetext-cell-events-section.md)
    
- [Character 内容](character-section.md)中的单元格
    
- [Paragraph 内容](paragraph-section.md)中的单元格
    
- [Tabs 内容](tabs-section.md)中的单元格
    
## <a name="remarks"></a>说明

要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**ReplaceLockText**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ReplaceLockText  <br/> |
   
若要从某个程序按索引获取对**ReplaceLockText**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowReplaceBehaviors** <br/> |
| 单元格索引：  <br/> |**visReplaceLockText** <br/> |
   

