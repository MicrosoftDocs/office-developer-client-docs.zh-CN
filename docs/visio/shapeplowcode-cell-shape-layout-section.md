---
title: ShapePlowCode 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm900
localization_priority: Normal
ms.assetid: acf07fd7-6aa6-1a92-9b7a-bd6fea8a7cb2
description: 确定在绘图页上在一个可放置形状旁放置另一个可放置形状时此形状是否移开。
ms.openlocfilehash: 6e155103f7bfc70a78826297f441fc9ce78942ad
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32325604"
---
# <a name="shapeplowcode-cell-shape-layout-section"></a>ShapePlowCode 单元格（“Shape Layout”内容）

确定在绘图页上在一个可放置形状旁放置另一个可放置形状时此形状是否移开。
  
|**Value**|**说明**|**自动常量**|
|:-----|:-----|:-----|
|0  <br/> |按页上指定绘制。  <br/> |**visSLOPlowDefault** <br/> |
|1  <br/> |不绘制任何形状。  <br/> |**visSLOPlowNever** <br/> |
|双面  <br/> |绘制每一个形状。  <br/> |**visSLOPlowAlways** <br/> |
   
## <a name="remarks"></a>注解

您还可以在 "行为" 对话框中的 "**放置**" 选项卡上为特定形状设置此单元格的值 (在选定形状的**情况**下, 在 "[开发工具](run-in-developer-mode-display-the-developer-tab.md)" 选项卡上的 "**形状设计**" 组中, 单击 "**行为**", 然后单击"**放置**" 选项卡)。 
  
若要为绘图页上的*所有*形状设置此行为, 请使用 "页面布局" 部分中的 "PlowCode" 单元格。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShapePlowCode 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |ShapePlowCode  <br/> |
   
若要从某个程序按索引获取对 ShapePlowCode 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowShapeLayout** <br/> |
|单元格索引：  <br/> |**visSLOPlowCode** <br/> |
   

