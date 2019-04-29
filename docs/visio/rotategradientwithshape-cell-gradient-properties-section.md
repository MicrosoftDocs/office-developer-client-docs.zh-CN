---
title: RotateGradientWithShape 单元格 ("渐变属性" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6aada005-3403-4666-9779-7ccb5b83b74a
description: 确定是否以布尔值的形式在2d 旋转中将填充渐变旋转。
ms.openlocfilehash: 76a76a4a97128c81710269f75e9e17db90827377
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412217"
---
# <a name="rotategradientwithshape-cell-gradient-properties-section"></a>RotateGradientWithShape 单元格 ("渐变属性" 部分)

确定是否以布尔值的形式在2d 旋转中将填充渐变旋转。
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |当形状围绕旋转针旋转时, 渐变将随形状旋转。 渐变的 "顶部" 平行于旋转控点。  <br/> |
|FALSE  <br/> |当形状围绕旋转针旋转时, 渐变不随形状旋转。 渐变的 "顶部" 平行于绘图画布。  <br/> |
   
## <a name="remarks"></a>说明

若要从另一个公式按名称获取对**RotateGradientWithShape**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | RotateGradientWithShape  <br/> |
   
若要从某个程序按索引获取对**RotateGradientWithShape**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowGradientProperties** <br/> |
| 单元格索引：  <br/> |**visRotateGradientWithShape** <br/> |
   

