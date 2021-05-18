---
title: 'RotationType Cell (3-D Rotation Properties Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a8d5388a-8fd0-4c6e-9633-e1f03c5bef3b
description: 确定形状是按照从 0 到 6 的整数进行平行旋转、透视旋转还是倾斜旋转。
ms.openlocfilehash: 676f8a15185242aacc1affb9f1bd200ff3df454d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422941"
---
# <a name="rotationtype-cell-3-d-rotation-properties-section"></a>RotationType Cell (3-D Rotation Properties Section) 

确定形状是按照从 0 到 6 的整数进行平行旋转、透视旋转还是倾斜旋转。 
  
|**值**|**说明**|
|:-----|:-----|
|0  <br/> |形状没有任何旋转。  <br/> |
|1  <br/> |形状具有平行旋转。  <br/> |
|2  <br/> |形状具有透视旋转。  <br/> |
|3  <br/> |形状具有左上倾斜旋转。  <br/> |
|4   <br/> |形状有右上倾斜旋转。  <br/> |
|5   <br/> |形状左下倾斜旋转。  <br/> |
|6   <br/> |形状有右下倾斜旋转。  <br/> |
   
## <a name="remarks"></a>备注

若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **RotationType** 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |RotationType  <br/> |
   
若要从程序按索引获取对 **RotationType** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRow3DRotationProperties** <br/> |
|单元格索引：  <br/> |**visRotationType** <br/> |
   

