---
title: ShdwOffsetY 单元格（“Page Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm930
localization_priority: Normal
ms.assetid: f3f53a7d-7450-b2b0-b508-6044a87450d9
description: 确定形状的投影与该形状垂直偏移的距离（按页面单位）。
ms.openlocfilehash: be7ec4cccd53cc9d74811e2e45122c8bc29497d3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438139"
---
# <a name="shdwoffsety-cell-page-properties-section"></a>ShdwOffsetY 单元格（“Page Properties”内容）

确定形状的投影与该形状垂直偏移的距离（按页面单位）。
  
## <a name="remarks"></a>说明

此值在 **“页面设置”** 对话框（在 **“设计”** 选项卡上，单击 **“页面设置”** 箭头）中设置。此值与绘图的缩放比例无关。即使绘图按比例缩放，阴影偏移量也仍保持不变。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShdwOffsetY 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ShdwOffsetY  <br/> |
   
若要从某个程序按索引获取对 ShdwOffsetY 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPage** <br/> |
| 单元格索引：  <br/> |**visPageShdwOffsetY** <br/> |
   

