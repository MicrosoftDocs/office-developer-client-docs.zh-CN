---
title: BlockSizeY 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm110
localization_priority: Normal
ms.assetid: be51e18e-ea49-0788-1a17-866090afb9f4
description: 确定垂直块大小，当您使用"设计"选项卡上的"配置布局"对话框 (在"布局"组中单击"Re-Layout 页面"，然后单击"其他布局选项") 来布局形状时，绘图页上每个形状都必须适合的区域。
ms.openlocfilehash: 08f2012bb027267810c21ef253a0073bb42d3a96
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427400"
---
# <a name="blocksizey-cell-page-layout-section"></a>BlockSizeY 单元格（“Page Layout”内容）

确定垂直块大小，当您使用"设计"选项卡上的"配置布局"对话框 (在"布局"组中单击"重新布局页面"，然后单击"其他布局选项 **")** 来布局形状时，绘图页上每个形状都必须适合的区域。
  
## <a name="remarks"></a>备注

您还可以在 **“布局与排列间距”** 对话框（在 **“设计”** 选项卡上，单击 **“页面设置”** 组中的箭头，单击 **“布局与排列”** 选项卡，然后单击 **“间距”**）中设置此值。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 BlockSizeY 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | BlockSizeY  <br/> |
   
若要从某个程序按索引获取对 BlockSizeY 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPageLayout** <br/> |
| 单元格索引：  <br/> |**visPLOBlockSizeY** <br/> |
   

