---
title: ReplaceLockShapeData 单元格 ("更改形状行为" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6a089266-7b19-4310-8cb5-4373ea3b2d64
description: 指示主控形状中指定单元格的值是否覆盖在形状替换操作过程中要替换的形状的值 (包括本地值)。 ReplaceLockShapeData 确定主控形状的形状数据是否覆盖正在替换的形状的所有形状数据。
ms.openlocfilehash: d2349da96bde7d141aada9066d56a4379f425fee
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348340"
---
# <a name="replacelockshapedata-cell-change-shape-behavior-section"></a>ReplaceLockShapeData 单元格 ("更改形状行为" 部分)

指示主控形状中指定单元格的值是否覆盖在形状替换操作过程中要替换的形状的值 (包括本地值)。 **ReplaceLockShapeData**确定主控形状的形状数据是否覆盖正在替换的形状的所有形状数据。 
  
|**Value**|**说明**|
|:-----|:-----|
|1 (TRUE)  <br/> |将主控形状的 "**形状数据**" 部分的所有行和值复制到替换形状上, 并丢弃替换旧形状中的任何本地值。  <br/> |
|0 (FALSE)  <br/> |将主控形状的 "**形状数据**" 部分的行和值复制到替换形状。 具有本地值的旧形状的 "**形状数据**" 部分中的任何行都将转换为替代形状。  <br/> |
   
## <a name="remarks"></a>注解

若要从另一个公式按名称获取对**ReplaceLockShapeData**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ReplaceLockShapeData  <br/> |
   
若要从某个程序按索引获取对**ReplaceLockShapeData**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowReplaceBehaviors** <br/> |
| 单元格索引：  <br/> |**visReplaceLockShapeData** <br/> |
   

