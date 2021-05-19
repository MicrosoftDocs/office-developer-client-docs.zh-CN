---
title: 'LineGradientEnabled Cell (Gradient Properties Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 276a661f-d14e-404a-a494-ae36601a8ce3
description: 确定是否为形状的线条或边框启用线条渐变。
ms.openlocfilehash: 1d2b33275d26bb0c8e5550bcb7cf282c64d34544
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416375"
---
# <a name="linegradientenabled-cell-gradient-properties-section"></a>LineGradientEnabled Cell (Gradient Properties Section) 

确定是否为形状的线条或边框启用线条渐变。 
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |渐变显示在形状的线条或边框上。  <br/> |
|FALSE  <br/> |渐变不显示在形状的线条或边框上。  <br/> |
   
## <a name="remarks"></a>备注

若要从另一个公式、Cell 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **LineGradientEnabled** 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LineGradientEnabled  <br/> |
   
若要从程序按索引获取对 **LineGradientEnabled** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowGradientProperties** <br/> |
| 单元格索引：  <br/> |**visLineGradientEnabled** <br/> |
   

