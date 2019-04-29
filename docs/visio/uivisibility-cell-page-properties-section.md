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
ms.openlocfilehash: 51ccd34cb40c286fe6b61818aea5a6b9c0b6d1a4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437327"
---
# <a name="uivisibility-cell-page-properties-section"></a>UIVisibility 单元格（“Page Properties”内容）

确定用户界面 (UI) 中是否显示页名称。
  
|**值**|**说明**|**自动常量**|
|:-----|:-----|:-----|
|0  <br/> |在 UI 中显示页名称（默认值）。  <br/> |**visUIVNormal** <br/> |
|1  <br/> |在 UI 中不显示页名称。  <br/> |**visUIVHidden** <br/> |
   
## <a name="remarks"></a>说明

通过将 UIVisibility 单元格设置为 **visUIVHidden**，可避免 UI 中在出现含有页名称的字符串的任何位置显示该页。 例如，该页不会作为 **“绘图资源管理器”** 中的选项列出，也不会在页标签上列出。 但是, 如果您使用的自动化或 UI 路径不包含页面名称, 例如 "**打印**" 命令, 则页面仍可访问。 
  
 此单元格设计用于文档页；而不是用于标记贴页，标记贴页的 UIVisibility 单元格默认设置为 **visUIVHidden**，并且不应改变。 
  
> [!NOTE]
> 若要从文档的**打印**命令中隐藏页面, 请将其设置为不用作任何页面的背景的背景页面 (**Type**属性为**visTypeBackground** ) (背景页面上的形状在使用它作为背景的页面上打印)打印)。 文档的**打印**命令仅适用于索引页, 并且不会对背景页编制索引。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 UIVisibility 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |UIVisibility  <br/> |
   
若要从某个程序按索引获取对 UIVisibility 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowPage** <br/> |
|单元格索引：  <br/> |**visPageUIVisibility** <br/> |
   

