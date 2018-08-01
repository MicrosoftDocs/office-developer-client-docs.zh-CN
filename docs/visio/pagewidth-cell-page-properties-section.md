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
ms.openlocfilehash: e03696c8f1c921c930d3563e9c73ef4ae613a7c1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780848"
---
# <a name="pagewidth-cell-page-properties-section"></a>PageWidth 单元格（“Page Properties”部分）

确定以绘图单位表示的打印页面的宽度。
  
## <a name="remarks"></a>注解

您还可以在**页面设置**对话框的**页面大小**选项卡上设置页宽 （在**设计**选项卡上，单击**页面设置**箭头） 或手动调整鼠标的页面。 若要执行此操作，请在按住 CTRL 键的同时拖动页上的边缘。 
  
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
   

