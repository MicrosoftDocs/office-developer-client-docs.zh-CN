---
title: 'ReplaceLockText Cell (Change Shape Behavior Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 31f43ebe-3758-4fd9-83b5-775041c5890f
description: 指示主控形状中指定单元格的值是否覆盖形状 (替换操作) 替换的形状的本地值。 ReplaceLockText 确定主控形状上显示的文本是否覆盖要替换的形状的文本。
ms.openlocfilehash: 299bd571ad935886879abb11108c3d0bd28e3183
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411916"
---
# <a name="replacelocktext-cell-change-shape-behavior-section"></a>ReplaceLockText Cell (Change Shape Behavior Section) 

指示主控形状中指定单元格的值是否覆盖形状 (替换操作) 替换的形状的本地值。 **ReplaceLockText** 确定主控形状上显示的文本是否覆盖要替换的形状的文本。 
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> | 主控形状上的文本将覆盖旧形状上的文本。 此外，主控形状在形状替换操作期间将覆盖以下各节中单元格的值：  <br/> **"文本字段"** 部分  <br/> **"文本块格式"** 部分  <br/> |
|FALSE  <br/> |替换形状包含已添加到该形状的旧形状的任何文本、文本字段或其他文本属性。  <br/> 当替换形状包含旧形状的文本属性时，如果替换形状具有多行，则替换形状还包含旧形状的 **"Character"** 和 **"Paragraph"** 内容中的值。  <br/> |
   
如果设置为 TRUE (1) ，则形状主控形状的值将替换要替换的形状上的下列值：
  
- [TheText Cell (Events Section)](thetext-cell-events-section.md)
    
- ["Character"内容中的单元格](character-section.md)
    
- Paragraph [内容中的单元格](paragraph-section.md)
    
- ["Tabs"内容中的单元格](tabs-section.md)
    
## <a name="remarks"></a>备注

若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **ReplaceLockText** 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ReplaceLockText  <br/> |
   
若要从程序按索引获取对 **ReplaceLockText** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowReplaceBehaviors** <br/> |
| 单元格索引：  <br/> |**visReplaceLockText** <br/> |
   

