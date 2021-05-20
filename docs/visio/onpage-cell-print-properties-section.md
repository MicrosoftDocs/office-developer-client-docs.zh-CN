---
title: OnPage 单元格（“Print Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033793
localization_priority: Normal
ms.assetid: 4015506a-e24a-0276-c854-7791a7019067
description: 指示是否将绘图打印到指定数量的打印纸上。
ms.openlocfilehash: 61d45a5bffdbb1afd5db9c608f80bc4f797f5191
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439602"
---
# <a name="onpage-cell-print-properties-section"></a>OnPage 单元格（“Print Properties”内容）

指示是否将绘图打印到指定数量的打印纸上。 
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |使绘图页适合定义的打印页数。  <br/> |
|FALSE  <br/> |不调整绘图页的大小以使其适合指定数量的打印纸（默认值）。  <br/> |
   
## <a name="remarks"></a>备注

如果 OnPage 单元格设置为 TRUE，则 Microsoft Visio 将使用 PagesX 单元格和 PagesY 单元格来确定适合于该绘图的打印页的数目。ScaleX 单元格和 ScaleY 单元格中的值将被忽略。可以将此设置视为“自动缩放”设置。
  
此值对应于"设计"选项卡上"页面设置"对话框中"打印设置"选项卡 ("调整为"选项，单击"页面设置"箭头) 。   
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 OnPage 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |OnPage  <br/> |
   
若要从某个程序按索引获取对 OnPage 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowPrintProperties** <br/> |
|单元格索引：  <br/> |**visPrintPropertiesOnPage** <br/> |
   

