---
title: BevelTopType 单元格 ("棱台属性" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3e29af0d-4183-41d1-8b0f-96450089f882
description: 确定形状的上边缘的斜面类型。
ms.openlocfilehash: 225600a3e39ec58622bcd8597e1115a52cb62a3f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315727"
---
# <a name="beveltoptype-cell-bevel-properties-section"></a>BevelTopType 单元格 ("棱台属性" 部分)

确定形状的上边缘的斜面类型。 
  
|**Value**|**说明**|
|:-----|:-----|
|0  <br/> |无棱台  <br/> |
|1  <br/> |圆形棱台  <br/> |
|双面  <br/> |松散内陷棱台  <br/> |
|第三章  <br/> |交叉棱台  <br/> |
|4  <br/> |酷斜面棱台  <br/> |
|5  <br/> |角斜面  <br/> |
|型  <br/> |柔圆棱台  <br/> |
|步  <br/> |凸棱台  <br/> |
|utf-8  <br/> |斜面棱台  <br/> |
|第  <br/> |草皮棱台  <br/> |
|10  <br/> |Riblet 棱台  <br/> |
|11x17  <br/> |硬边缘棱台  <br/> |
|12  <br/> |艺术装饰棱台  <br/> |
   
## <a name="remarks"></a>注解

若要从另一个公式按名称获取对**BevelTopType**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |BevelTopType  <br/> |
   
若要从某个程序按索引获取对**BevelTopType**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowBevelProperties** <br/> |
|单元格索引：  <br/> |**visBevelTopType** <br/> |
   

