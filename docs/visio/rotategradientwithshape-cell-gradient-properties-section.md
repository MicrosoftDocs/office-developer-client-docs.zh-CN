---
title: 'RotateGradientWithShape Cell (Gradient Properties Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6aada005-3403-4666-9779-7ccb5b83b74a
description: 确定填充渐变是否随形状在 2D 旋转中作为布尔值旋转。
ms.openlocfilehash: 76a76a4a97128c81710269f75e9e17db90827377
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412217"
---
# <a name="rotategradientwithshape-cell-gradient-properties-section"></a>RotateGradientWithShape Cell (Gradient Properties Section) 

确定填充渐变是否随形状在 2D 旋转中作为布尔值旋转。
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |当形状围绕旋转中心点旋转时，渐变随形状一起旋转。 渐变的"顶部"与旋转手柄平行。  <br/> |
|FALSE  <br/> |当形状围绕旋转中心点旋转时，该渐变不会随形状一起旋转。 渐变的"顶部"与绘图画布平行。  <br/> |
   
## <a name="remarks"></a>备注

若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **RotateGradientWithShape** 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | RotateGradientWithShape  <br/> |
   
若要从程序按索引获取对 **RotateGradientWithShape** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowGradientProperties** <br/> |
| 单元格索引：  <br/> |**visRotateGradientWithShape** <br/> |
   

