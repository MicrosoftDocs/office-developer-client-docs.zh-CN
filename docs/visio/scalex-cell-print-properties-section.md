---
title: ScaleX 单元格（“Print Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60072
localization_priority: Normal
ms.assetid: 5916eadc-37f8-47af-fe54-f6062aea318f
description: 在打印纸上指定百分比的绘图页的放大倍数。
ms.openlocfilehash: 1713e88f06dc93a2806e64cae3d7af20c9df1fc8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781220"
---
# <a name="scalex-cell-print-properties-section"></a>ScaleX 单元格（“Print Properties”部分）

在打印纸上指定百分比的绘图页的放大倍数。
  
## <a name="remarks"></a>说明

仅当 OnPage 单元格的值为 FALSE 时，才使用此值。 ScaleX 和 ScaleY 单元格始终具有相同的值，此名称对应于**页面设置**对话框中**打印设置**选项卡上的**调整为**设置中的值 （**设计**选项卡中，单击**页面设置**箭头）。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ScaleX 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |ScaleX  <br/> |
   
若要从某个程序按索引获取对 ScaleX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowPrintProperties** <br/> |
|单元格索引：  <br/> |**visPrintPropertiesScaleX** <br/> |
   

