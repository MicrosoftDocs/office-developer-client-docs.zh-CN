---
title: ShapeSplittable 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60081
localization_priority: Normal
ms.assetid: 6330304a-71f3-62b4-1b27-14495e3f12c3
description: 指示此一维形状是否可以拆分。
ms.openlocfilehash: 9f92cf7d147be8e59d860bcc8a958bf0cdc008c6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427071"
---
# <a name="shapesplittable-cell-shape-layout-section"></a>ShapeSplittable 单元格（“Shape Layout”内容）

指示此一维形状是否可以拆分。 
  
|**值**|**说明**|**自动常量**|
|:-----|:-----|:-----|
| 0  <br/> | 不允许拆分此形状。  <br/> |**visSLOSplittableNone** <br/> |
| 1  <br/> | 允许拆分此形状。  <br/> |**visSLOSplittableAllow** <br/> |
   
## <a name="remarks"></a>备注

连接线和其他一维形状的默认行为取决于绘图类型。 
  
形状的自动拆分是在三个不同级别上启用和禁用的：应用程序、页面和形状。默认情况下，在应用程序和页面级别上启用拆分。 
  
若要在应用程序级别启用或禁用拆分，请使用 **"Visio** 选项"对话框的"高级"选项卡上的"启用连接器拆分"设置 (单击"文件"选项卡，单击"选项"，然后单击"高级) "。   
  
若要启用/禁用页面拆分，请参阅 [PageShapeSplit](pageshapesplit-cell-page-layout-section.md) 单元格。 
  
若要使某个形状可以拆分其他一维可拆分形状，请参阅 [ShapeSplit](shapesplit-cell-shape-layout-section.md) 单元格。 
  
若要从另一个公式或使用 **CellsU** 属性从程序按名称获取对 ShapeSplittable 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ShapeSplittable  <br/> |
   
若要从某个程序按索引获取对 ShapeSplittable 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowShapeLayout** <br/> |
| 单元格索引：  <br/> |**visSLOSplittable** <br/> |
   

