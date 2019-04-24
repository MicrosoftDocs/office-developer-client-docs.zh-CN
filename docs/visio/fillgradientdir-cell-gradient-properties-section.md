---
title: FillGradientDir 单元格 ("渐变属性" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e8156ff1-c540-44b8-8b69-ba4d54883260
description: 确定填充渐变的方向。 渐变可以是线形、放射状、矩形或跟随路径。
ms.openlocfilehash: 53aad056c7fc1674e00e142fd72a10134103b390
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322461"
---
# <a name="fillgradientdir-cell-gradient-properties-section"></a>FillGradientDir 单元格 ("渐变属性" 部分)

确定填充渐变的方向。 渐变可以是线形、放射状、矩形或跟随路径。 
  
> [!NOTE]
> 线性渐变是唯一采用其他角度值 (由**FillGradientDir**单元格确定) 的渐变。 其他所有渐变方向都具有预设枚举。 
  
****

|**Value**|**说明**|
|:-----|:-----|
|0  <br/> |线性渐变。 **FillGradientAngle**单元格决定渐变的方向。  <br/> |
|1-7  <br/> |放射状渐变。 渐变从一个中心点向外扩展到一个圆。  <br/> |
|8-12  <br/> |矩形渐变。 渐变将作为方向线从具有矩形形状淡入淡出的原点扩展。  <br/> |
|13  <br/> |路径渐变。  <br/> |
   
## <a name="remarks"></a>注解

若要从另一个公式按名称获取对**FillGradientDir**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | FillGradientDir  <br/> |
   
若要从某个程序按索引获取对**FillGradientDir**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowGradientProperties** <br/> |
| 单元格索引：  <br/> |**visFillGradientDir** <br/> |
   

