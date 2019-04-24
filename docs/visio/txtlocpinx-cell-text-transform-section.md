---
title: TxtLocPinX 单元格（“Text Transform”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251275
localization_priority: Normal
ms.assetid: cbfc4e91-10d1-d50e-3e8a-f269f7123276
description: 确定文本块的旋转中心相对于文本块原点的 x 轴坐标值。 默认公式为：
ms.openlocfilehash: 390f8129e8000a043969eda0ab1c8e4ef62515ef
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316448"
---
# <a name="txtlocpinx-cell-text-transform-section"></a>TxtLocPinX 单元格（“Text Transform”内容）

确定文本块的旋转中心相对于文本块原点的*x*轴坐标值。 默认公式为： 
  
= TxtWidth \* 0。5
  
该公式计算文本块的水平中心。
  
## <a name="remarks"></a>注解

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 TxtLocPinX 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | TxtLocPinX  <br/> |
   
要从某个程序按索引获取对 TxtLocPinX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowTextXForm** <br/> |
| 单元格索引：  <br/> |**visXFormLocPinX** <br/> |
   

