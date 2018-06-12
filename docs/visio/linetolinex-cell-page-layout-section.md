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
ms.openlocfilehash: aa6476eab9d5bcf7aab12235fd23f0f5675d6ad5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780578"
---
# <a name="linetolinex-cell-page-layout-section"></a>LineToLineX 单元格（“Page Layout”内容）

确定在绘图页上所有连接线之间的水平间距。
  
## <a name="remarks"></a>注解

在**布局与排列间距**对话框中，您还可以设置此单元格的值。 （在**设计**选项卡上，单击**页面设置**箭头，单击**布局与排列**，然后单击**间距**。）
  
要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 LineToLineX 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |LineToLineX  <br/> |
   
若要从某个程序按索引获取对 LineToLineX 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowPageLayout** <br/> |
|单元格索引：  <br/> |**visPLOLineToLineX** <br/> |
   

