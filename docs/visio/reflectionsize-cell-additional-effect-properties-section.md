---
title: 'ReflectionSize Cell (Additional Effect Properties Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 7dfeb78e-a0fa-4492-b35f-70b1e2975d38
description: 确定相对于形状的反射大小，以 0.0% 到 100.0% 的百分比表示。 ReflectionSize 单元格中值为 0% 的形状没有反射;值 100% 显示形状的完整镜像。
ms.openlocfilehash: 60fcb315ec1b6187082bdcdbbdcfaa4b80bbcfb3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409074"
---
# <a name="reflectionsize-cell-additional-effect-properties-section"></a>ReflectionSize Cell (Additional Effect Properties Section) 

确定相对于形状的反射大小，以 0.0% 到 100.0% 的百分比表示。 **ReflectionSize** 单元格中值为 0% 的形状没有反射;值 100% 显示形状的完整镜像。 
  
## <a name="remarks"></a>备注

若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 CellsU 属性从某个程序按名称获取对 **ReflectionSize** 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ReflectionSize  <br/> |
   
若要从程序按索引获取对 **ReflectionSize** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowOtherEffectProperties** <br/> |
| 单元格索引：  <br/> |**visReflectionSize** <br/> |
   

