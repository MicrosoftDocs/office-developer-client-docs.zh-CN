---
title: BlockSizeX 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm105
localization_priority: Normal
ms.assetid: 253aac17-077e-48e0-39a8-a3abd5d4a257
description: 确定水平块大小, 当您使用 "配置布局" 对话框 (在 "设计" 选项卡上的 "布局" 组中, 单击 "重新布局页面", 然后单击 "其他布局选项") 排放形状时, 绘图页上每个形状都必须符合的区域。
ms.openlocfilehash: 8e4cee4b2059d9b8f2fe77c2d4902e67246eac2f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424187"
---
# <a name="blocksizex-cell-page-layout-section"></a>BlockSizeX 单元格（“Page Layout”内容）

确定水平块大小, 当您使用 "**配置布局**" 对话框 (在 "**设计**" 选项卡上的 "布局" 组中的 "**布局**" 组中, 单击 "**重新布局页面") 排放形状时, 绘图页上每个形状都必须符合的区域。**, 然后单击 "**其他布局选项**"。
  
## <a name="remarks"></a>说明

您还可以在 **“布局与排列间距”** 对话框（在 **“设计”** 选项卡上，单击 **“页面设置”** 组中的箭头，单击 **“布局与排列”** 选项卡，然后单击 **“间距”**）中设置此值。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 BlockSizeX 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |BlockSizeX  <br/> |
   
若要从某个程序按索引获取对 BlockSizeX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPageLayout** <br/> |
| 单元格索引：  <br/> |**visPLOBlockSizeX** <br/> |
   

