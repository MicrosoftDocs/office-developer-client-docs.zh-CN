---
title: 'LineGradientDir Cell (Gradient Properties Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c603f9a5-f887-47ce-90bb-d41ec2d1a6a1
description: 确定线条渐变的方向。 渐变可以是线性、径向、矩形或遵循路径。
ms.openlocfilehash: 05dcc6904a4e67d97c632dba44635936b1c14049
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417985"
---
# <a name="linegradientdir-cell-gradient-properties-section"></a>LineGradientDir Cell (Gradient Properties Section) 

确定线条渐变的方向。 渐变可以是线性、径向、矩形或遵循路径。 
  
> [!NOTE]
> 线性渐变是唯一一个采用其他角度值的渐变 (**由 LineGradientDir** 单元格值) 。 所有其他渐变方向都有预设枚举。 
  
|**值**|**说明**|
|:-----|:-----|
|0  <br/> |线性渐变。 **LineGradientAngle** 单元格确定渐变的方向。  <br/> |
|1-7  <br/> |径向渐变。 渐变从中心点向外延伸，在圆中向外延伸。  <br/> |
|8-12  <br/> |矩形渐变。 渐变从具有矩形淡化的原点延伸为方向线。  <br/> |
|13  <br/> |路径渐变。  <br/> |
   
## <a name="remarks"></a>备注

若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **LineGradientDir** 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LineGradientDir  <br/> |
   
若要从程序按索引获取对 **LineGradientDir** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowGradientProperties** <br/> |
| 单元格索引：  <br/> |**visLineGradientDir** <br/> |
   

