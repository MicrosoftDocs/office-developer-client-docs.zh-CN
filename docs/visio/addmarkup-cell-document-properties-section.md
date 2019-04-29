---
title: AddMarkup 单元格（“Document Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1030801
localization_priority: Normal
ms.assetid: 46146424-b4c9-2240-36c0-19bb35ec51d1
description: 指示是否正对文档进行审阅以便加标记。
ms.openlocfilehash: 4e0860639b0d89fce2c35a8947bd5ac00fcc63e5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427631"
---
# <a name="addmarkup-cell-document-properties-section"></a>AddMarkup 单元格（“Document Properties”内容）

指示是否正对文档进行审阅以便加标记。
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |正在对文档进行审阅。  <br/> |
|FALSE  <br/> |未对文档进行审阅（默认值）。  <br/> |
   
## <a name="remarks"></a>说明

当 AddMarkup 单元格设置为 TRUE 时，审阅者正在添加标记，并且更改将应用于标记贴页而不是原始绘图页。 当 AddMarkup 单元格为 FALSE 时，将禁用标记跟踪，并且更改将应用于原始绘图页。
  
> [!NOTE]
> 您可以使用 GUARD 函数阻止对文档进行标记。 如果 AddMarkup 单元格包含公式 = GUARD (FALSE), 则禁用 "**跟踪标记**" 命令。 
  
此设置对应于 **“审阅”** 选项卡上的 **“标记”** 组中的 **“跟踪标记”** 命令设置。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 AddMarkup 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |AddMarkup  <br/> |
   
若要从某个程序按索引获取对 AddMarkup 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowDoc** <br/> |
|单元格索引：  <br/> |**visDocAddMarkup** <br/> |
   

