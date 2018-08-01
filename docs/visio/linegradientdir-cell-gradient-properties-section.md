---
title: LineGradientDir 单元格（“Gradient Properties”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c603f9a5-f887-47ce-90bb-d41ec2d1a6a1
description: 确定线条渐变的方向。 渐变可以是线性、 径向、 矩形，或按路径。
ms.openlocfilehash: 6243d7a6b470db0915ba6fc462f05b72a9814f66
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780581"
---
# <a name="linegradientdir-cell-gradient-properties-section"></a>LineGradientDir 单元格（“Gradient Properties”部分）

确定线条渐变的方向。 渐变可以是线性、 径向、 矩形，或按路径。 
  
> [!NOTE]
> 线性渐变是采用其他角度值 （如由**LineGradientDir**单元格） 的唯一渐变。 所有其他渐变方向具有预设枚举。 
  
|**值**|**说明**|
|:-----|:-----|
|0  <br/> |线性渐变。 **LineGradientAngle**单元格确定渐变的方向。  <br/> |
|1-7  <br/> |径向渐变。 渐变扩展向外圆圈从一个中心点。  <br/> |
|8-12  <br/> |矩形渐变。 渐变扩展为方向一行与矩形形状淡来源。  <br/> |
|13  <br/> |路径渐变。  <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**LineGradientDir**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LineGradientDir  <br/> |
   
若要从某个程序按索引获取对**LineGradientDir**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowGradientProperties** <br/> |
| 单元格索引：  <br/> |**visLineGradientDir** <br/> |
   

