---
title: LineGradientEnabled 单元格（“Gradient Properties”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 276a661f-d14e-404a-a494-ae36601a8ce3
description: 确定是否将行渐变启用了线条或形状边框。
ms.openlocfilehash: d78a94a25c0290bd5e58522c9a45955868f31b32
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780562"
---
# <a name="linegradientenabled-cell-gradient-properties-section"></a>LineGradientEnabled 单元格（“Gradient Properties”部分）

确定是否将行渐变启用了线条或形状边框。 
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |渐变的线条或形状边框上显示。  <br/> |
|FALSE  <br/> |行或形状边框上不显示渐变。  <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**LineGradientEnabled**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LineGradientEnabled  <br/> |
   
若要从某个程序按索引获取对**LineGradientEnabled**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowGradientProperties** <br/> |
| 单元格索引：  <br/> |**visLineGradientEnabled** <br/> |
   

