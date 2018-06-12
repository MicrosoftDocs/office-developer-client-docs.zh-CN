---
title: ShdwOffsetX 单元格（“Page Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251373
localization_priority: Normal
ms.assetid: 92ec9b11-f53f-a1c9-832a-6cac08aa5379
description: 确定形状的投影与该形状水平偏移的距离（按页面单位）。
ms.openlocfilehash: 9aec108146e329d7a8161acc4ca7cdcb19424eff
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781325"
---
# <a name="shdwoffsetx-cell-page-properties-section"></a>ShdwOffsetX 单元格（“Page Properties”内容）

确定形状的投影与该形状水平偏移的距离（按页面单位）。
  
## <a name="remarks"></a>注解

在**页面设置**对话框设置此值 （**设计**选项卡中，单击**页面设置**箭头）。 此值是比例的绘图无关。 缩放绘图时，如果阴影偏移量保持不变。 
  
要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 ShdwOffsetX 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ShdwOffsetX  <br/> |
   
若要从某个程序按索引获取对 ShdwOffsetX 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPage** <br/> |
| 单元格索引：  <br/> |**visPageShdwOffsetX** <br/> |
   

