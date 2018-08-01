---
title: ReplaceLockShapeData 单元格（“Change Shape Behavior”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6a089266-7b19-4310-8cb5-4373ea3b2d64
description: 指示在主控形状中的指定单元格的值是否覆盖形状替换操作期间要替换的形状 （包括本地值） 的值。 ReplaceLockShapeData 确定是否主控形状的形状数据将覆盖所有要替换的形状的形状数据。
ms.openlocfilehash: 07547140c7c96e49663270e51a90fd559afedf29
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781093"
---
# <a name="replacelockshapedata-cell-change-shape-behavior-section"></a>ReplaceLockShapeData 单元格（“Change Shape Behavior”部分）

指示在主控形状中的指定单元格的值是否覆盖形状替换操作期间要替换的形状 （包括本地值） 的值。 **ReplaceLockShapeData**确定是否主控形状的形状数据将覆盖所有要替换的形状的形状数据。 
  
|**值**|**说明**|
|:-----|:-----|
|1 (TRUE)  <br/> |所有的行和主控形状的**形状数据**部分的值复制到的替换形状，要替换的旧形状中的所有本地值将被丢弃。  <br/> |
|0 (FALSE)  <br/> |行和值**形状数据**部分中的主控形状复制到的替换形状。 **形状数据**部分中的旧形状本地值与任何行被转接到的替换形状。  <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**ReplaceLockShapeData**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ReplaceLockShapeData  <br/> |
   
若要从某个程序按索引获取对**ReplaceLockShapeData**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowReplaceBehaviors** <br/> |
| 单元格索引：  <br/> |**visReplaceLockShapeData** <br/> |
   

