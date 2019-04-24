---
title: LineToLineX 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm565
localization_priority: Normal
ms.assetid: f6b461fe-56ac-4c0e-31cd-6b3c1075db6e
description: 确定在绘图页上所有连接线之间的水平间距。
ms.openlocfilehash: f3dbf43c737fef1fa1156fb4dc8d0f23449328c0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358952"
---
# <a name="linetolinex-cell-page-layout-section"></a>LineToLineX 单元格（“Page Layout”内容）

确定在绘图页上所有连接线之间的水平间距。
  
## <a name="remarks"></a>注解

您还可以在 **“布局与排列间距”** 对话框中设置此单元格的值。（在 **“设计”** 选项卡上，单击 **“页面设置”** 箭头，再单击 **“布局与排列”**，然后单击 **“间距”**。）
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LineToLineX 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |LineToLineX  <br/> |
   
若要从某个程序按索引获取对 LineToLineX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowPageLayout** <br/> |
|单元格索引：  <br/> |**visPLOLineToLineX** <br/> |
   

