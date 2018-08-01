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
ms.openlocfilehash: 69430122b0a7665d7daa4a6b28f3a51745b74473
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779645"
---
# <a name="addmarkup-cell-document-properties-section"></a>AddMarkup 单元格（“Document Properties”部分）

指示是否正对文档进行审阅以便加标记。
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |正在对文档进行审阅。  <br/> |
|FALSE  <br/> |未对文档进行审阅（默认值）。  <br/> |
   
## <a name="remarks"></a>注解

AddMarkup 单元格设置为 true，则审阅者时添加标记和更改应用于标记贴页面不的原始绘图页。 AddMarkup 单元格时为 FALSE，跟踪标记处于关闭状态，并更改应用于原始绘图页。
  
> [!NOTE]
> 可以对您的文档使用 GUARD 函数防止标记。 如果 AddMarkup 单元格包含公式 = GUARD(FALSE)，禁用**跟踪标记**命令。 
  
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
   

