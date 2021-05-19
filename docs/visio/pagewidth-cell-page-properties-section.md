---
title: PageWidth 单元格（“Page Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251372
localization_priority: Normal
ms.assetid: b98c5bf3-10c8-7299-2836-3906d6a9135d
description: 确定以绘图单位表示的打印页面的宽度。
ms.openlocfilehash: 6d887cb4335d2725101db54ba2b1483ccf01cff4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434268"
---
# <a name="pagewidth-cell-page-properties-section"></a>PageWidth 单元格（“Page Properties”内容）

确定以绘图单位表示的打印页面的宽度。
  
## <a name="remarks"></a>备注

您还可以在"页面设置"对话框的"页面大小"选项卡上设置页面宽度 (在"设计"选项卡上，单击"页面设置"箭头) 或者使用鼠标手动调整页面大小。 若要手动调整页面大小，请按住 Ctrl 键，同时拖动页面的边缘。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 PageWidth 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |PageWidth  <br/> |
   
若要从某个程序按索引获取对 PageWidth 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowPage** <br/> |
|单元格索引：  <br/> |**visPageWidth** <br/> |
   

