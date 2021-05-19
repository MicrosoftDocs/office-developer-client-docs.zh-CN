---
title: PageHeight 单元格（“Page Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm760
localization_priority: Normal
ms.assetid: 0184814c-2d67-6ad4-e336-5694612e518d
description: 包含以绘图单位表示的打印页面的高度。
ms.openlocfilehash: ac24bee517f29da333a445f276447c1aa682f01c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427078"
---
# <a name="pageheight-cell-page-properties-section"></a>PageHeight 单元格（“Page Properties”内容）

包含以绘图单位表示的打印页面的高度。
  
## <a name="remarks"></a>备注

还可以在 **“页面设置”** 对话框（在 **“设计”** 选项卡上，单击 **“页面设置”** 箭头）的 **“页面尺寸”** 选项卡上设置页面高度，或使用鼠标手动调整页面大小。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 PageHeight 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |PageHeight  <br/> |
   
若要从某个程序按索引获取对 PageHeight 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowPage** <br/> |
|单元格索引：  <br/> |**visPageHeight** <br/> |
   

