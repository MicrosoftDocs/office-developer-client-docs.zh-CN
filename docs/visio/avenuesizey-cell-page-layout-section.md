---
title: AvenueSizeY 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm70
localization_priority: Normal
ms.assetid: 9ff2893c-afe5-505e-0b55-48ec1de08a5f
description: 确定使用配置布局对话框排放形状时在绘图页上的形状之间的垂直空间量 （在设计选项卡上的布局组中，单击重新布局页面，然后单击更多布局选项）。
ms.openlocfilehash: af4089a3b215efaf49b8a45929ca94799fffcba5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779668"
---
# <a name="avenuesizey-cell-page-layout-section"></a>AvenueSizeY 单元格（“Page Layout”内容）

确定使用**配置布局**对话框排放形状时在绘图页上的形状之间的垂直空间量 （**设计**选项卡上，在**布局**组中，单击**重新布局**页面，然后单击**更多布局选项**)。
  
## <a name="remarks"></a>备注

您还可以在**布局与排列间距**对话框来设置此值 （**设计**选项卡中，单击**页面设置**组中的箭头，单击**布局和路由**选项卡，然后单击**间距**）。
  
只有一个形状时可用于计算垂直间距，动态网格 AvenueSizeY 单元格中使用的设置。 在**视图**选项卡上的**视觉帮助**组中，使用动态网格中，选择**动态网格**。
  
若要获取对 AvenueSizeY 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | AvenueSizeY  <br/> |
   
若要从某个程序按索引获取对 AvenueSizeY 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPageLayout** <br/> |
| 单元格索引：  <br/> |**visPLOAvenueSizeY** <br/> |
   

