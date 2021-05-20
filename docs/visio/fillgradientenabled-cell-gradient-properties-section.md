---
title: 'FillGradientEnabled Cell (Gradient Properties Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 80db9c0c-13c6-47de-967f-ade6e5899f14
description: 确定是否为此形状启用填充渐变。
ms.openlocfilehash: 17f617c13b632318be22b86a3354a194f0f835f5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431209"
---
# <a name="fillgradientenabled-cell-gradient-properties-section"></a>FillGradientEnabled Cell (Gradient Properties Section) 

确定是否为此形状启用填充渐变。 
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |渐变填充显示在形状上。  <br/> |
|FALSE  <br/> |渐变填充不显示在形状上。  <br/> |
   
## <a name="remarks"></a>备注

若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **FillGradientEnabled** 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | FillGradientEnabled  <br/> |
   
若要从程序按索引获取对 **FillGradientEnabled** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowGradientProperties** <br/> |
| 单元格索引：  <br/> |**visFillGradientEnabled ** <br/> |
   

