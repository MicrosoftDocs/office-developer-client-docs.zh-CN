---
title: ReplaceLockFormat 单元格（“Change Shape Behavior”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6973e2e6-7e7f-48ba-95b3-37c959f6ffb1
description: 指示在主控形状中的指定单元格的值是否覆盖形状替换操作期间要替换的形状 （包括本地值） 的值。 如果主控形状的 ReplaceLockFormat 单元格设置为 TRUE (1)，主控形状的格式值覆盖由主控形状的形状的所有相应值。
ms.openlocfilehash: bf1e28353cc1e2d737a7d7a6dcd90caf14e19dc8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781071"
---
# <a name="replacelockformat-cell-change-shape-behavior-section"></a>ReplaceLockFormat 单元格（“Change Shape Behavior”部分）

指示在主控形状中的指定单元格的值是否覆盖形状替换操作期间要替换的形状 （包括本地值） 的值。 如果主控形状的**ReplaceLockFormat**单元格设置为 TRUE (1)，主控形状的格式值覆盖由主控形状的形状的所有相应值。 
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |如果主控形状的**ReplaceLockFormat**单元格设置为 TRUE，主控形状的格式值覆盖由主控形状的形状的所有相应值。  <br/> |
|FALSE  <br/> |如果主控形状的**ReplaceLockFormat**单元格设置为 FALSE，替换形状在替换操作后包含旧的形状的本地格式值。  <br/> |
   
## <a name="remarks"></a>说明

**ReplaceLockFormat**单元格确定主控形状是否覆盖形状替换操作过程中的以下各节中的单元格的本地格式值： 
  
- **填充格式**部分 
    
- **行格式**部分 
    
- **快速样式**部分 
    
- **主题属性**部分 
    
- **渐变**properties 
    
- **凹凸效果属性**部分 
    
- **其他效果属性**部分 
    
- **行渐变光圈**部分 
    
- **填充的渐变光圈**部分 
    
要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**ReplaceLockFormat**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ReplaceLockFormat  <br/> |
   
若要从某个程序按索引获取对**ReplaceLockFormat**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowReplaceBehaviors** <br/> |
| 单元格索引：  <br/> |**visReplaceLockFormat** <br/> |
   

