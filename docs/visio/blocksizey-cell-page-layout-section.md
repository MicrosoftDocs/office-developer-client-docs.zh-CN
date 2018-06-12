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
description: 确定垂直块大小，其中每个形状中的区域必须适合绘图页，使用配置布局对话框排放形状时 （在设计选项卡上的布局组中，单击重新布局页面，然后单击更多布局选项）。
ms.openlocfilehash: 283723bf902c07cfb044ab73107491df3c170a4d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779782"
---
# <a name="blocksizey-cell-page-layout-section"></a>BlockSizeY 单元格（“Page Layout”内容）

确定垂直块大小，其中每个形状中的区域必须适合绘图页，使用**配置布局**对话框排放形状时 （在**设计**选项卡的**布局**组中，单击**Re 布局页**上，然后单击**更多布局选项**)。
  
## <a name="remarks"></a>备注

您还可以在**布局与排列间距**对话框来设置此值 （**设计**选项卡中，单击**页面设置**组中的箭头，单击**布局和路由**选项卡，然后单击**间距**）。
  
若要获取对 BlockSizeY 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | BlockSizeY  <br/> |
   
若要从某个程序按索引获取对 BlockSizeY 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPageLayout** <br/> |
| 单元格索引：  <br/> |**visPLOBlockSizeY** <br/> |
   

