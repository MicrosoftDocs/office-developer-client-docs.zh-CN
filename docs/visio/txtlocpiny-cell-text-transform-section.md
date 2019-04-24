---
title: TxtLocPinY 单元格（“Text Transform”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251276
localization_priority: Normal
ms.assetid: 3f46cfcf-7eac-4a37-e782-39f4e7f8fc43
description: 确定文本块的旋转中心相对于文本块起点的 y 轴坐标值。 默认公式为：
ms.openlocfilehash: 937c4e9928d32d55e8336d192b1ecc6140fd8381
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317729"
---
# <a name="txtlocpiny-cell-text-transform-section"></a>TxtLocPinY 单元格（“Text Transform”内容）

确定文本块的旋转中心相对于文本块起点的*y*轴坐标值。 默认公式为： 
  
= TxtHeight \* 0。5
  
## <a name="remarks"></a>注解

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 TxtLocPinY 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | TxtLocPinY  <br/> |
   
要从某个程序按索引获取对 TxtLocPinY 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowTextXForm** <br/> |
| 单元格索引：  <br/> |**visXFormLocPinY** <br/> |
   

