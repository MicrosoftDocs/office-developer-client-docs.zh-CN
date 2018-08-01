---
title: RotationType 单元格（“3-D Rotation Properties”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a8d5388a-8fd0-4c6e-9633-e1f03c5bef3b
description: 确定形状遵循并行旋转、 角度旋转或倾斜旋转，为从 0 到 6 的整数。
ms.openlocfilehash: 85effcef3969d7b7c57551ec88710ba84b3fc163
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781155"
---
# <a name="rotationtype-cell-3-d-rotation-properties-section"></a>RotationType 单元格（“3-D Rotation Properties”部分）

确定形状遵循并行旋转、 角度旋转或倾斜旋转，为从 0 到 6 的整数。 
  
|**值**|**说明**|
|:-----|:-----|
|0  <br/> |形状没有任何旋转。  <br/> |
|1  <br/> |形状具有并行旋转。  <br/> |
|2  <br/> |形状的旋转角度。  <br/> |
|3  <br/> |形状的顶部左侧倾斜旋转角度。  <br/> |
|4  <br/> |形状的顶部的倾斜朝右旋转。  <br/> |
|5  <br/> |形状的底部左侧倾斜旋转。  <br/> |
|6  <br/> |形状具有底部右键倾斜旋转。  <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**RotationType**单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |RotationType  <br/> |
   
若要从某个程序按索引获取对**RotationType**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRow3DRotationProperties** <br/> |
|单元格索引：  <br/> |**visRotationType** <br/> |
   

