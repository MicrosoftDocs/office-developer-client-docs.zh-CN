---
title: RotateGradientWithShape 单元格（“Gradient Properties”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6aada005-3403-4666-9779-7ccb5b83b74a
description: 确定是否填充渐变旋转 2D 旋转，作为一个布尔值中的形状。
ms.openlocfilehash: d752f870fd08c1a47dfc7ce193b6976a1bdb2a1f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781111"
---
# <a name="rotategradientwithshape-cell-gradient-properties-section"></a>RotateGradientWithShape 单元格（“Gradient Properties”部分）

确定是否填充渐变旋转 2D 旋转，作为一个布尔值中的形状。
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |围绕旋转 pin 旋转该形状时，与形状旋转渐变。 平行旋转手柄"顶部"的渐变。  <br/> |
|FALSE  <br/> |围绕旋转 pin 旋转该形状时将渐变不与形状旋转。 平行于绘图画布"顶部"的渐变。  <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**RotateGradientWithShape**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | RotateGradientWithShape  <br/> |
   
若要从某个程序按索引获取对**RotateGradientWithShape**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowGradientProperties** <br/> |
| 单元格索引：  <br/> |**visRotateGradientWithShape** <br/> |
   

