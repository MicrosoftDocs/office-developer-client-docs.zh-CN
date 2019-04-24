---
title: 关于“公式跟踪”窗口
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
f1_keywords:
- Vis_DSS.chm60118
localization_priority: Normal
ms.assetid: 0cdacd4e-74dc-32c3-2eb2-219bf7fcb532
description: “公式跟踪”窗口用来向形状开发人员提供与单元格之间相互依赖关系有关的信息 — 这些单元格既包括从属单元格（与给定单元格有从属关系的单元格），也包括引用单元格（给定单元格所依赖的单元格）。
ms.openlocfilehash: f5f9d6a7ba3ab7049715d31342cfe7aa68ea053f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345310"
---
# <a name="about-the-formula-tracing-window"></a>关于“公式跟踪”窗口

**“公式跟踪”** 窗口用来向形状开发人员提供与单元格之间相互依赖关系有关的信息 — 这些单元格既包括从属单元格（与给定单元格有从属关系的单元格），也包括引用单元格（给定单元格所依赖的单元格）。 
  
Microsoft Visio ShapeSheet 中的单元格含有值和公式。 同样, 公式可以引用其他单元格, 从而能够根据另一个单元格的值计算一个单元格中的值。 但是，在创建或维护复杂形状时，可能很难确定所有这些相互依赖关系，因为公式可以引用绘图中的任何单元格，无论是同一 ShapeSheet 中的单元格，还是属于绘图中的其他对象（例如，页面、样式、主控形状或其他形状）的单元格。 
  
"**公式跟踪**" 窗口提供的信息可帮助您了解对单元格所做更改的影响。 
  
## <a name="displaying-the-formula-tracing-window"></a>显示 "公式跟踪" 窗口

若要查看 "**公式跟踪**" 窗口, 在 shapesheet 窗口处于活动状态时, 在 "窗 shapesheet**工具**" 的 "* * 设计 * *" 选项卡上的 "**公式跟踪**" 组中, 单击 "**显示窗口**"。 默认情况下, "**公式跟踪**" 窗口显示为停靠在 ShapeSheet 窗口中, 但它是一个锚定窗口, 可停靠、浮动或与其他可用的锚定 ShapeSheet 窗口 (例如, "**样式资源管理器**" 窗口) 合并。 
  
## <a name="tracing-dependent-cells"></a>追踪从属单元格

要查看从属于某个特定单元格的单元格的列表，请在 ShapeSheet 窗口中选择该单元格。在本例中，选择了 Width 单元格。 
  
![Width 单元格处于选中状态](media/ShapeSheetDependents_UI_01_ZA01039814.gif)
  
若要查看其从属单元格, 请在 "**公式跟踪**" 组中, 单击 "**追踪从属**单元格"。
  
从属于 Width 单元格的所有单元格的列表将出现在 **“公式跟踪”** 窗口中。通过双击 **“公式跟踪”** 窗口中的条目，您可以浏览到该列表中的任何单元格。 
  
![对 Width 单元格具有依赖关系的所有单元格都将显示在 "公式跟踪" 窗口中](media/ShapeSheetDependents_UI_02_ZA01039815.gif)
  
## <a name="tracing-precendent-cells"></a>跟踪 precendent 单元格

要查看某个特定单元格所依赖的单元格列表，请在 ShapeSheet 窗口中选择该单元格。在本例中，选择了 Geometry1.X2 单元格。 
  
![已选择 "geometry1.path" 单元格](media/ShapeSheetPrecedents_UI_01_ZA01039817.gif)
  
若要查看其引用单元格, 请在 "**公式跟踪**" 组中, 单击 "**追踪引用单元**格"。
  
geometry1.path 单元格所依赖的所有单元格的列表显示在 "**公式跟踪**" 窗口中。 通过双击 **“公式跟踪”** 窗口中的条目，您可以浏览到该列表中的任何单元格。 
  
![geometry1.path 单元格所依赖的所有单元格都显示在 "公式跟踪" 窗口中](media/ShapeSheetPrecedents_UI_02_ZA01039818.gif)
  

