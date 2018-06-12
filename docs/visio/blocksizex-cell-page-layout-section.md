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
description: 确定水平块大小，其中每个形状中的区域必须适合绘图页，使用配置布局对话框排放形状时 （在设计选项卡上的布局组中，单击重新布局页面，然后单击更多布局选项）。
ms.openlocfilehash: 68ed13b85583326c25635049d7e85babe62d5eb5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779778"
---
# <a name="blocksizex-cell-page-layout-section"></a>BlockSizeX 单元格（“Page Layout”内容）

确定水平块大小，其中每个形状中的区域必须适合绘图页，使用**配置布局**对话框排放形状时 （在**设计**选项卡的**布局**组中，单击**Re 布局页**，，然后单击**更多布局选项**)。
  
## <a name="remarks"></a>备注

您还可以在**布局与排列间距**对话框来设置此值 （**设计**选项卡中，单击**页面设置**组中的箭头，单击**布局和路由**选项卡，然后单击**间距**）。
  
若要获取对 BlockSizeX 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |BlockSizeX  <br/> |
   
若要从某个程序按索引获取对 BlockSizeX 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPageLayout** <br/> |
| 单元格索引：  <br/> |**visPLOBlockSizeX** <br/> |
   

