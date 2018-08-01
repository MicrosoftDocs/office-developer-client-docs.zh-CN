---
title: Active 单元格（“Layers”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm10
localization_priority: Normal
ms.assetid: 4c8e366f-9e9b-30ea-a89f-57c8d7a1168e
description: 指定图层是否处于活动状态。将形状拖到绘图页上时，未预先分配图层的形状将指定给活动图层。
ms.openlocfilehash: 81d3ec083e207a927c46dda99e2b7f42c0a7bd8e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779627"
---
# <a name="active-cell-layers-section"></a>Active 单元格（“Layers”部分）

指定图层是否处于活动状态。将形状拖到绘图页上时，未预先分配图层的形状将指定给活动图层。
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |
          图层是活动图层。
  <br/> |
|FALSE  <br/> |
          图层不是活动图层。
  <br/> |
   
## <a name="remarks"></a>说明

此单元格中的值对应于 **“图层属性”** 对话框（在 **“开始”** 选项卡上的 **“编辑”** 组中，单击 **“图层”**，然后单击 **“图层属性”**）中的 **“活动”** 设置。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Active 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |Layers.Active [ *i* ] 其中*i* = < 1 >，2，3...  <br/> |
   
若要从某个程序按索引获取对 Active 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionLayer** <br/> |
|行索引：  <br/> |**visRowLayer** +  *i*其中*i* = 0、 1、 2...  <br/> |
|单元格索引：  <br/> |**visLayerActive** <br/> |
   

