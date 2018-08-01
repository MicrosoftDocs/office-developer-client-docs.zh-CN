---
title: LineToLineY 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm570
localization_priority: Normal
ms.assetid: db9a8232-25c5-7087-2ae9-50470d0cf16e
description: 确定在绘图页上所有连接线之间的垂直间距。
ms.openlocfilehash: 781d166fe0b81cc2402fde2894cd1d0480a0895f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780583"
---
# <a name="linetoliney-cell-page-layout-section"></a>LineToLineY 单元格（“Page Layout”部分）

确定在绘图页上所有连接线之间的垂直间距。
  
## <a name="remarks"></a>注解

您还可以在 **“布局与排列间距”** 对话框中设置此单元格的值。（在 **“设计”** 选项卡上，单击 **“页面设置”** 箭头，再单击 **“布局与排列”**，然后单击 **“间距”**。）
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LineToLineY 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |LineToLineY  <br/> |
   
若要从某个程序按索引获取对 LineToLineY 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowPageLayout** <br/> |
|单元格索引：  <br/> |**visPLOLineToLineY** <br/> |
   

