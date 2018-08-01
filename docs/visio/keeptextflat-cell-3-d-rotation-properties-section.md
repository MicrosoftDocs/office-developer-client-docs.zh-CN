---
title: KeepTextFlat 单元格（“3-D Rotation Properties”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3537de44-8d6f-4bd9-bf8c-fa851fc007b9
description: 指示是否将形状的文本将忽略三维形状的旋转角度。 不应用于二维旋转。
ms.openlocfilehash: cf8b964360e602b81a2a7b7ca79961921eeeb8b7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780513"
---
# <a name="keeptextflat-cell-3-d-rotation-properties-section"></a>KeepTextFlat 单元格（“3-D Rotation Properties”部分）

指示是否将形状的文本将忽略三维形状的旋转角度。 不应用于二维旋转。 
  
****

|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |与形状的几何形状文本不一起旋转。  <br/> |
|FALSE  <br/> |形状文本进行转换，以与形状的几何旋转。  <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**KeepTextFlat**单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |KeepTextFlat  <br/> |
   
若要从某个程序按索引获取对**KeepTextFlat**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRow3DRotationProperties** <br/> |
|单元格索引：  <br/> |**visKeepTextFlat** <br/> |
   

