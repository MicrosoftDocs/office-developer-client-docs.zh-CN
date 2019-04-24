---
title: ResizePage 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm850
localization_priority: Normal
ms.assetid: d63fe874-1027-3436-dbc1-73e722bce22e
description: 确定在使用“配置布局”对话框（在“设计”选项卡上的“布局”组中，单击“重新布局页面”，然后单击“其他布局选项”）排放形状后是否放大页面以装入绘图。
ms.openlocfilehash: 8d0001ce35808f8c5f11068ed78865ce992af5cb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326822"
---
# <a name="resizepage-cell-page-layout-section"></a>ResizePage 单元格（“Page Layout”内容）

确定在使用 "**配置布局**" 对话框 (在 "**设计**" 选项卡上的 "**布局**" 组中, 单击 "**重新布局**页面", 然后单击 "**其他布局") 排放形状后是否放大页面以将绘图放在该对话框的上方。选项**)。
  
|**Value**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 放大页面。  <br/> |
| FALSE  <br/> | 不放大页面。  <br/> |
   
## <a name="remarks"></a>注解

若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ResizePage 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ResizePage  <br/> |
   
若要从某个程序按索引获取对 ResizePage 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPageLayout** <br/> |
| 单元格索引：  <br/> |**visPLOResizePage** <br/> |
   

