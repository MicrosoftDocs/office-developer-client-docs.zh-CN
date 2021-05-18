---
title: 'ReplaceLockShapeData Cell (Change Shape Behavior Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6a089266-7b19-4310-8cb5-4373ea3b2d64
description: 指示主控形状中指定单元格的值是否覆盖形状 (替换操作) 替换的形状的本地值。 ReplaceLockShapeData 确定主形状的形状数据是否覆盖要替换的形状的所有形状数据。
ms.openlocfilehash: d2349da96bde7d141aada9066d56a4379f425fee
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408871"
---
# <a name="replacelockshapedata-cell-change-shape-behavior-section"></a>ReplaceLockShapeData Cell (Change Shape Behavior Section) 

指示主控形状中指定单元格的值是否覆盖形状 (替换操作) 替换的形状的本地值。 **ReplaceLockShapeData** 确定主形状的形状数据是否覆盖要替换的形状的所有形状数据。 
  
|**值**|**说明**|
|:-----|:-----|
|1 (TRUE)   <br/> |主控形状的 **"形状数据** "部分的所有行和值都复制到替换形状中，并丢弃被替换的旧形状的任何本地值。  <br/> |
|0 (FALSE)   <br/> |主控形状的 **"形状数据** "内容中的行和值将复制到替换形状。 具有本地值的旧 **形状** 的"形状数据"部分的任何行都将被转移到替换形状。  <br/> |
   
## <a name="remarks"></a>备注

若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **ReplaceLockShapeData** 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ReplaceLockShapeData  <br/> |
   
若要从程序按索引获取对 **ReplaceLockShapeData** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowReplaceBehaviors** <br/> |
| 单元格索引：  <br/> |**visReplaceLockShapeData** <br/> |
   

