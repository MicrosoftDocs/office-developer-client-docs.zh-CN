---
title: PageScale 单元格（“Page Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm775
localization_priority: Normal
ms.assetid: e1da84b3-fd15-12b9-9342-0412e818b3b9
description: 确定当前绘图比例中页面单位的值。页面的绘图比例是 PageScale 单元格中显示的页面单位与 DrawingScale 单元格中显示的绘图单位之比。
ms.openlocfilehash: 0e1721ea667ad3bcd9f35880ab4e63bc90802c32
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780870"
---
# <a name="pagescale-cell-page-properties-section"></a>PageScale 单元格（“Page Properties”部分）

确定当前绘图比例中页面单位的值。页面的绘图比例是 PageScale 单元格中显示的页面单位与 DrawingScale 单元格中显示的绘图单位之比。
  
## <a name="remarks"></a>注解

您还可以在 **“页面设置”** 对话框（在 **“设计”** 选项卡上，单击 **“页面设置”** 箭头）中的 **“绘图缩放比例”** 选项卡上设置 PageScale 单元格的值。该单元格的值是 **“预定义缩放比例”** 框或 **“自定义缩放比例”** 框中两个数字中的第一个数字，具体情况则取决于在 **“绘图缩放比例”** 下选择的绘图缩放比例设置。例如，如果为绘图选择结构缩放比例，则该页的绘图缩放比例为 3/32" = 1'0"。PageScale 单元格中的值为 0.0938 in.（或 3/32"），DrawingScale 单元格中的值为 1 ft。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 PageScale 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |PageScale  <br/> |
   
若要从某个程序按索引获取对 PageScale 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowPage** <br/> |
|单元格索引：  <br/> |**visPageScale** <br/> |
   

