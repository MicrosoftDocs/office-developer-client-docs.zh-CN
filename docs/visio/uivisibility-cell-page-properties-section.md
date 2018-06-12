---
title: UIVisibility 单元格（“Page Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60090
localization_priority: Normal
ms.assetid: df7f79df-770a-4868-e7e2-05c3828e23eb
description: 确定用户界面 (UI) 中是否显示页名称。
ms.openlocfilehash: dcb4a14ff89c7f5c77916e6b188aaf87e1711ab0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781611"
---
# <a name="uivisibility-cell-page-properties-section"></a>UIVisibility 单元格（“Page Properties”内容）

确定用户界面 (UI) 中是否显示页名称。
  
|**值**|**说明**|**自动化常量**|
|:-----|:-----|:-----|
|0  <br/> |在 UI 中显示页名称（默认值）。  <br/> |**visUIVNormal** <br/> |
|1  <br/> |在 UI 中不显示页名称。  <br/> |**visUIVHidden** <br/> |
   
## <a name="remarks"></a>备注

将 UIVisibility 单元格设置为**visUIVHidden**可防止页包含页面名称的字符串的显示位置在 UI 中任意位置显示。 例如，页上不会列为**绘图资源管理器**中或在页面选项卡上的选项。 页面仍然可以访问，但是，如果您使用自动化或 UI 不包括页名称，例如，**打印**命令的路径。 
  
 此单元格旨在用于文档页面; 例如：它不能用于标记贴页面，具有默认设置为**visUIVHidden** UIVisibility 单元格，并不应被更改。 
  
> [!NOTE]
> 若要隐藏页上，从文档的**打印**命令，使其将背景页 （**Type**属性是**visTypeBackground** ） 不使用作为背景由任何页面 （当使用作为背景页打印页面的背景上的形状打印）。 文档的**打印**命令仅处理索引页和背景页不编制索引。 
  
若要获取对 UIVisibility 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |UIVisibility  <br/> |
   
若要从某个程序按索引获取对 UIVisibility 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowPage** <br/> |
|单元格索引：  <br/> |**visPageUIVisibility** <br/> |
   

