---
title: RotationType 单元格 ("三维旋转属性" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a8d5388a-8fd0-4c6e-9633-e1f03c5bef3b
description: 确定形状是采用平行旋转、透视旋转还是倾斜旋转, 为0到6的整数。
ms.openlocfilehash: 676f8a15185242aacc1affb9f1bd200ff3df454d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315671"
---
# <a name="rotationtype-cell-3-d-rotation-properties-section"></a>RotationType 单元格 ("三维旋转属性" 部分)

确定形状是采用平行旋转、透视旋转还是倾斜旋转, 为0到6的整数。 
  
|**Value**|**说明**|
|:-----|:-----|
|0  <br/> |形状没有任何旋转。  <br/> |
|1  <br/> |形状具有平行旋转。  <br/> |
|双面  <br/> |形状具有透视旋转。  <br/> |
|第三章  <br/> |形状具有左上角倾斜旋转。  <br/> |
|4  <br/> |形状具有右上角倾斜旋转。  <br/> |
|5  <br/> |形状具有左下角倾斜旋转。  <br/> |
|型  <br/> |形状具有右下角倾斜旋转。  <br/> |
   
## <a name="remarks"></a>注解

若要从另一个公式按名称获取对**RotationType**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |RotationType  <br/> |
   
若要从某个程序按索引获取对**RotationType**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRow3DRotationProperties** <br/> |
|单元格索引：  <br/> |**visRotationType** <br/> |
   

