---
title: ShapeShdwShow 单元格（“Fill Format”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ece6c889-9291-40ea-b55a-072acdcb8a52
description: 确定形状是否将阴影，显示为从 0 到 2 的整数。
ms.openlocfilehash: 72077e60089acd3cd3f8a9349691e1468f6b1f9c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781290"
---
# <a name="shapeshdwshow-cell-fill-format-section"></a>ShapeShdwShow 单元格（“Fill Format”部分）

确定形状是否将阴影，显示为从 0 到 2 的整数。
  
|**值**|**说明**|
|:-----|:-----|
|0  <br/> |如果指定阴影，始终显示阴影。 不显示的子形状阴影。  <br/> |
|1  <br/> |除非形状没有父不呈现阴影。 如果组合在一起，请使用子形状阴影。  <br/> |
|2  <br/> |如果指定阴影，始终显示阴影。 显示的子形状阴影。  <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**ShapeShdwShow**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ShapeShdwShow  <br/> |
   
若要从某个程序按索引获取对**ShapeShdwShow**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowFill** <br/> |
| 单元格索引：  <br/> |**visFillShdwShow** <br/> |
   

