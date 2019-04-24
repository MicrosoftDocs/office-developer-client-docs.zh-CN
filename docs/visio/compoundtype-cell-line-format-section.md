---
title: CompoundType 单元格 ("Line Format" 内容)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3e2a88ad-d92c-4550-8da3-fa7fdd032e73
description: 确定形状的线条的复合类型。
ms.openlocfilehash: 120975e419656234266cb8151b2fa37ef19602e5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359365"
---
# <a name="compoundtype-cell-line-format-section"></a>CompoundType 单元格 ("Line Format" 内容)

确定形状的线条的复合类型。 
  
|**Value**|**说明**|
|:-----|:-----|
|0  <br/> |简单  <br/> |
|1  <br/> |双精度  <br/> |
|双面  <br/> |粗细  <br/> |
|第三章  <br/> |细厚  <br/> |
|4  <br/> |Triple  <br/> |
   
## <a name="remarks"></a>注解

若要从另一个公式按名称获取对**CompoundType**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | CompoundType  <br/> |
   
若要从某个程序按索引获取对**CompoundType**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowLine** <br/> |
| 单元格索引：  <br/> |**visCompoundType** <br/> |
   

