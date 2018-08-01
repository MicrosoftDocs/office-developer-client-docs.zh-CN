---
title: PageShapeSplit 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033777
localization_priority: Normal
ms.assetid: 4d3bdf77-0ad4-86a4-d215-1d5a5fbe33f7
description: 指示是否可以自动拆分页面上的形状。
ms.openlocfilehash: 7f1df0158cde6853c5518597c853cb56151eefbc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780845"
---
# <a name="pageshapesplit-cell-page-layout-section"></a>PageShapeSplit 单元格（“Page Layout”部分）

指示是否可以自动拆分页面上的形状。
  
|**值**|**说明**|**自动常量**|
|:-----|:-----|:-----|
|0  <br/> |不允许自动拆分形状。  <br/> |**visPLOSplitNone** <br/> |
|1  <br/> |允许自动拆分形状（默认值）。  <br/> |**visPLOSplitAllow** <br/> |
   
## <a name="remarks"></a>注解

形状的自动拆分是在三个不同级别上启用和禁用的：应用程序、页面和形状。默认情况下，在应用程序和页面级别上启用拆分。形状的默认设置随绘图类型的不同而不同。 
  
若要启用或禁用应用程序级别拆分，请使用**启用连接线拆分**设置**Visio 选项**对话框的**高级**选项卡 （单击**Office**按钮，单击**Visio** **选项**选项卡，然后单击**高级**）。 
  
若要启用或禁用拆分在形状级别，请参阅 ShapeSplit 和 ShapeSplittable 单元格。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 PageShapeSplit 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |PageShapeSplit  <br/> |
   
若要从某个程序按索引获取对 PageShapeSplit 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowPageLayout** <br/> |
|单元格索引：  <br/> |**visPLOSplit** <br/> |
   

