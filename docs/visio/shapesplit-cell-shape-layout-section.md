---
title: ShapeSplit 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60080
localization_priority: Normal
ms.assetid: 96b8c503-67b3-8623-d99b-0dad7b15c224
description: 指示此形状是否可以拆分其他可拆分的形状。
ms.openlocfilehash: b782977bd5b7e828223675eb16f4e7e48f4ca55d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781297"
---
# <a name="shapesplit-cell-shape-layout-section"></a>ShapeSplit 单元格（“Shape Layout”内容）

指示此形状是否可以拆分其他可拆分的形状。
  
|**值**|**说明**|**自动化常量**|
|:-----|:-----|:-----|
| 0  <br/> | 不允许此形状拆分其他形状。  <br/> |**visSLOSplitNone** <br/> |
| 1  <br/> | 允许此形状拆分其他形状。  <br/> |**visSLOSplitAllow** <br/> |
   
## <a name="remarks"></a>注解

可以拆分其他形状的形状必须是二维形状或一维可放置形状。 
  
形状的自动拆分是在三个不同级别上启用和禁用的：应用程序、页面和形状。默认情况下，在应用程序和页面级别上启用拆分；形状的默认设置随绘图类型的不同而不同。 
  
若要启用或禁用应用程序级别拆分，请使用**启用连接线拆分**设置**Visio 选项**对话框的**高级**选项卡 （**文件**选项卡，单击**选项**，然后单击**高级**)。 
  
若要启用/禁用页面拆分，请参阅 PageShapeSplit 单元格。 
  
要使一维形状可以拆分，请参阅 ShapeSplittable 单元格。
  
若要获取对 ShapeSplit 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ShapeSplit  <br/> |
   
若要从某个程序按索引获取对 ShapeSplit 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowShapeLayout** <br/> |
| 单元格索引：  <br/> |**visSLOSplit** <br/> |
   

