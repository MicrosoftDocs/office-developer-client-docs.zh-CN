---
title: 'CompoundType Cell (Line Format Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3e2a88ad-d92c-4550-8da3-fa7fdd032e73
description: 确定形状线条的复合类型。
ms.openlocfilehash: 120975e419656234266cb8151b2fa37ef19602e5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407170"
---
# <a name="compoundtype-cell-line-format-section"></a>CompoundType Cell (Line Format Section) 

确定形状线条的复合类型。 
  
|**值**|**说明**|
|:-----|:-----|
|0  <br/> |简单  <br/> |
|1  <br/> |双精度  <br/> |
|2  <br/> |粗细  <br/> |
|3  <br/> |粗细  <br/> |
|4   <br/> |Triple  <br/> |
   
## <a name="remarks"></a>备注

若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 CellsU 属性从某个程序按名称获取对 **CompoundType** 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | CompoundType  <br/> |
   
若要从程序按索引获取对 **CompoundType** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowLine** <br/> |
| 单元格索引：  <br/> |**visCompoundType** <br/> |
   

