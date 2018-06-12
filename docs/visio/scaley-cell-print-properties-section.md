---
title: ScaleY 单元格（“Print Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033788
localization_priority: Normal
ms.assetid: 02835aff-455b-ffeb-d53b-28387b6ce361
description: 在打印纸上指定百分比的绘图页的放大倍数。
ms.openlocfilehash: 2735b2cfce04cc9a8d8da1a815081aaa5892c723
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781216"
---
# <a name="scaley-cell-print-properties-section"></a>ScaleY 单元格（“Print Properties”内容）

在打印纸上指定百分比的绘图页的放大倍数。
  
## <a name="remarks"></a>备注

仅当 OnPage 单元格的值为 FALSE 时，才使用此值。 ScaleX 和 ScaleY 单元格始终具有相同的值，此名称对应于**页面设置**对话框中**打印设置**选项卡上的**调整为**设置中的值 （**设计**选项卡中，单击**页面设置**箭头）。 
  
要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 ScaleY 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |ScaleY  <br/> |
   
若要从某个程序按索引获取对 ScaleY 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowPrintProperties** <br/> |
|单元格索引：  <br/> |**visPrintPropertiesScaleY** <br/> |
   

