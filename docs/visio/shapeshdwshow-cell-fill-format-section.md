---
title: 'ShapeShdwShow Cell (Fill Format Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ece6c889-9291-40ea-b55a-072acdcb8a52
description: 确定形状是否以 0 到 2 的整数显示阴影。
ms.openlocfilehash: 1da52c20acaa19eab79970a751fad2c225e212ae
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422115"
---
# <a name="shapeshdwshow-cell-fill-format-section"></a>ShapeShdwShow Cell (Fill Format Section) 

确定形状是否以 0 到 2 的整数显示阴影。
  
|**值**|**说明**|
|:-----|:-----|
|0  <br/> |如果指定阴影，则始终显示阴影。 不显示子形状的阴影。  <br/> |
|1  <br/> |除非形状没有父形状，否则不要呈现阴影。 如果组合在一起，请使用子形状阴影。  <br/> |
|2  <br/> |如果指定阴影，则始终显示阴影。 将显示子形状的阴影。  <br/> |
   
## <a name="remarks"></a>备注

若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 CellsU 属性从某个程序按名称获取对 **ShapeShdwShow** 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ShapeShdwShow  <br/> |
   
若要从程序按索引获取对 **ShapeShdwShow** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowFill** <br/> |
| 单元格索引：  <br/> |**visFillShdwShow** <br/> |
   

