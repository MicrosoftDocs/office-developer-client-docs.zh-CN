---
title: ShapeShdwShow 单元格 ("填充格式" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ece6c889-9291-40ea-b55a-072acdcb8a52
description: 确定形状是否显示阴影, 以从0到2的整数。
ms.openlocfilehash: 1da52c20acaa19eab79970a751fad2c225e212ae
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349145"
---
# <a name="shapeshdwshow-cell-fill-format-section"></a>ShapeShdwShow 单元格 ("填充格式" 部分)

确定形状是否显示阴影, 以从0到2的整数。
  
|**Value**|**说明**|
|:-----|:-----|
|0  <br/> |如果指定了阴影, 则始终显示阴影。 子形状的阴影不显示。  <br/> |
|1  <br/> |除非形状没有父级, 否则不要呈现阴影。 如果组合在一起, 请使用子形状阴影。  <br/> |
|双面  <br/> |如果指定了阴影, 则始终显示阴影。 将显示子形状的阴影。  <br/> |
   
## <a name="remarks"></a>注解

若要从另一个公式按名称获取对**ShapeShdwShow**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ShapeShdwShow  <br/> |
   
若要从某个程序按索引获取对**ShapeShdwShow**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowFill** <br/> |
| 单元格索引：  <br/> |**visFillShdwShow** <br/> |
   

