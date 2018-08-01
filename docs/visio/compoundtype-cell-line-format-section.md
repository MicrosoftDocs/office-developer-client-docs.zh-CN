---
title: CompoundType 单元格（“Line Format”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3e2a88ad-d92c-4550-8da3-fa7fdd032e73
description: 确定形状的行的复合类型。
ms.openlocfilehash: 663b683030251c8b57324f1d2bdf492463c50eef
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779923"
---
# <a name="compoundtype-cell-line-format-section"></a>CompoundType 单元格（“Line Format”部分）

确定形状的行的复合类型。 
  
|**值**|**说明**|
|:-----|:-----|
|0  <br/> |简单  <br/> |
|1  <br/> |双精度数  <br/> |
|2  <br/> |Thick 细  <br/> |
|3  <br/> |细粗  <br/> |
|4  <br/> |Triple  <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**CompoundType**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | CompoundType  <br/> |
   
若要从某个程序按索引获取对**CompoundType**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowLine** <br/> |
| 单元格索引：  <br/> |**visCompoundType** <br/> |
   

