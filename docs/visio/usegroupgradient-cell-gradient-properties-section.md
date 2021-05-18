---
title: 'UseGroupGradient Cell (Gradient Properties Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f1dcf0ec-8b4a-4ee1-9208-b1c84e30d37b
description: 确定形状与其他形状组合在一起时是否采用渐变，作为布尔值。 UseGroupGradient 单元格的值仅影响形状填充。
ms.openlocfilehash: a69b48095aec93705c686a5401051f1d1e368d18
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411363"
---
# <a name="usegroupgradient-cell-gradient-properties-section"></a>UseGroupGradient Cell (Gradient Properties Section) 

确定形状与其他形状组合在一起时是否采用渐变，作为布尔值。 **UseGroupGradient** 单元格的值仅影响形状填充。 
  
## <a name="remarks"></a>备注

若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **UseGroupGradient** 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | UseGroupGradient  <br/> |
   
若要从程序按索引获取对 **UseGroupGradient** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowGradientProperties** <br/> |
| 单元格索引：  <br/> |**visUseGroupGradient ** <br/> |
   

