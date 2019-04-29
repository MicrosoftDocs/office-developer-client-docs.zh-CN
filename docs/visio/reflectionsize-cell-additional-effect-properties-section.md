---
title: ReflectionSize 单元格 ("其他效果属性" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7dfeb78e-a0fa-4492-b35f-70b1e2975d38
description: 确定相对于形状的反射的大小, 以0.0 到 100.0% 的百分比。 ReflectionSize 单元格中值为 0% 的形状没有反射;100% 的值显示形状的完整镜像。
ms.openlocfilehash: 60fcb315ec1b6187082bdcdbbdcfaa4b80bbcfb3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409074"
---
# <a name="reflectionsize-cell-additional-effect-properties-section"></a>ReflectionSize 单元格 ("其他效果属性" 部分)

确定相对于形状的反射的大小, 以0.0 到 100.0% 的百分比。 **ReflectionSize**单元格中值为 0% 的形状没有反射;100% 的值显示形状的完整镜像。 
  
## <a name="remarks"></a>说明

若要从另一个公式按名称获取对**ReflectionSize**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ReflectionSize  <br/> |
   
若要从某个程序按索引获取对**ReflectionSize**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowOtherEffectProperties** <br/> |
| 单元格索引：  <br/> |**visReflectionSize** <br/> |
   

