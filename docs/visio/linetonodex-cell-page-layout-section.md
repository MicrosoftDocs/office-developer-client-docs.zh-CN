---
title: LineToNodeX 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm575
localization_priority: Normal
ms.assetid: 9d58e23e-b411-c5c1-b785-5014488d42c8
description: 确定在绘图页上所有连接线和形状之间的水平间距。
ms.openlocfilehash: c5a27edb25ce7b1449ad6e2988027b474bd79fdb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439707"
---
# <a name="linetonodex-cell-page-layout-section"></a>LineToNodeX 单元格（“Page Layout”内容）

确定在绘图页上所有连接线和形状之间的水平间距。
  
## <a name="remarks"></a>备注

您还可以在 **“布局与排列间距”** 对话框中设置此单元格的值。（在 **“设计”** 选项卡上，单击 **“页面设置”** 箭头，再单击 **“布局与排列”**，然后单击 **“间距”**。）
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LineToNodeY 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |LineToNodeX  <br/> |
   
若要从某个程序按索引获取对 LineToNodeX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowPageLayout** <br/> |
|单元格索引：  <br/> |**visPLOLineToNodeX** <br/> |
   

