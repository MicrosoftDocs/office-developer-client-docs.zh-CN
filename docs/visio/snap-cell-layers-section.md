---
title: Snap 单元格（“Layers”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251355
localization_priority: Normal
ms.assetid: c1b24e45-6f08-686b-b53d-e85fb9087a50
description: 确定其他形状是否可以与分配给图层的形状对齐。分配给图层的形状可以和其他形状对齐，但其他形状不能与它们对齐。
ms.openlocfilehash: 87e7e7500469fb7f8c7fdd4771a0225d0e4fc993
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359806"
---
# <a name="snap-cell-layers-section"></a>Snap 单元格（“Layers”内容）

确定其他形状是否可以与分配给图层的形状对齐。分配给图层的形状可以和其他形状对齐，但其他形状不能与它们对齐。
  
|**Value**|**说明**|
|:-----|:-----|
|TRUE  <br/> |其他形状可以和图层上的形状对齐。  <br/> |
|FALSE  <br/> |其他形状不能和图层上的形状对齐。  <br/> |
   
## <a name="remarks"></a>注解

还可以使用 **“图层属性”** 对话框（在 **“开始”** 选项卡上的 **“编辑”** 组中，单击 **“图层”**，然后单击 **“图层属性”**）中的 **“对齐”** 选项设置此单元格的值。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Snap 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |"层"。贴靠 [ *i* ] 其中*i* = <1>, 2, 3 .。。  <br/> |
   
若要从某个程序按索引获取对 Snap 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionLayer** <br/> |
|行索引：  <br/> |**visRowLayer** +  *i* = ** 0、1、2 .。。  <br/> |
|单元格索引：  <br/> |**visLayerSnap** <br/> |
   

