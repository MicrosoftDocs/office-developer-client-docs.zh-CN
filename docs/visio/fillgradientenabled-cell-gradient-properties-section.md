---
title: FillGradientEnabled 单元格 （渐变 Properties 内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 80db9c0c-13c6-47de-967f-ade6e5899f14
description: 确定是否启用此形状填充渐变。
ms.openlocfilehash: 20a38d4c45af163bc00364a45dc31269bf97251f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780258"
---
# <a name="fillgradientenabled-cell-gradient-properties-section"></a>FillGradientEnabled 单元格 （渐变 Properties 内容）

确定是否启用此形状填充渐变。 
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |渐变填充形状上显示。  <br/> |
|FALSE  <br/> |渐变填充形状上不显示。  <br/> |
   
## <a name="remarks"></a>备注

要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**FillGradientEnabled**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | FillGradientEnabled  <br/> |
   
若要从某个程序按索引获取对**FillGradientEnabled**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowGradientProperties** <br/> |
| 单元格索引：  <br/> |* * visFillGradientEnabled * * <br/> |
   

