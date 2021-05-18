---
title: 'KeepTextFlat Cell (3-D Rotation Properties Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3537de44-8d6f-4bd9-bf8c-fa851fc007b9
description: 指示形状的文本是否忽略该形状在三维中的旋转。 不适用于二维旋转。
ms.openlocfilehash: fc8cf2fac431645876c7f81ed9864cb6c2036169
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422038"
---
# <a name="keeptextflat-cell-3-d-rotation-properties-section"></a>KeepTextFlat Cell (3-D Rotation Properties Section) 

指示形状的文本是否忽略该形状在三维中的旋转。 不适用于二维旋转。 
  
****

|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |形状文本不随形状的几何图形一起旋转。  <br/> |
|FALSE  <br/> |形状文本会进行转换，以与形状的几何图形一起旋转。  <br/> |
   
## <a name="remarks"></a>备注

若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **KeepTextFlat** 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |KeepTextFlat  <br/> |
   
若要从程序按索引获取对 **KeepTextFlat** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRow3DRotationProperties** <br/> |
|单元格索引：  <br/> |**visKeepTextFlat** <br/> |
   

