---
title: ShapeShdwScaleFactor 单元格（“Fill Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033175
localization_priority: Normal
ms.assetid: 94ec06c5-8d2f-dd27-1eed-1abaf93daba8
description: 指定形状阴影可放大或缩小的百分比。
ms.openlocfilehash: 5862b61ca1f5df25ca97bf8742b9e20bf45091a9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436263"
---
# <a name="shapeshdwscalefactor-cell-fill-format-section"></a>ShapeShdwScaleFactor 单元格（“Fill Format”内容）

指定形状阴影可放大或缩小的百分比。
  
## <a name="remarks"></a>备注

每个阴影都有一个阴影的图钉位置，该位置是阴影上对应于形状的图钉的点。 例如，如果形状的固定位于形状的中心，则阴影的固定位置将是阴影的中心点。 将缩放应用于简单阴影时，缩放以阴影的图钉位置为中心;当将缩放应用于倾斜阴影时，缩放将应用于倾斜方向。 
  
要设置一页中所有形状的这个值，请使用“Page Properties”内容中的 ShdwScaleFactor 单元格。
  
此值对应于 **“阴影”** 对话框（在 **“开始”** 选项卡上的 **“形状”** 组中，单击 **“阴影”**，然后单击 **“阴影选项”**）中的 **“缩放”** 设置的值。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShapeShdwScaleFactor 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |ShapeShdwScaleFactor  <br/> |
   
若要从某个程序按索引获取对 ShapeShdwScaleFactor 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowFill** <br/> |
|单元格索引：  <br/> |**visFillShdwScaleFactor** <br/> |
   

