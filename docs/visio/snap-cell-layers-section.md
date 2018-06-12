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
ms.openlocfilehash: 7fc684afb67d0454ea5907c08f4f7644d97c7f74
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781383"
---
# <a name="snap-cell-layers-section"></a>Snap 单元格（“Layers”内容）

确定其他形状是否可以与分配给图层的形状对齐。分配给图层的形状可以和其他形状对齐，但其他形状不能与它们对齐。
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |其他形状可以和图层上的形状对齐。  <br/> |
|FALSE  <br/> |其他形状不能和图层上的形状对齐。  <br/> |
   
## <a name="remarks"></a>注解

您还可以设置此单元格，使用**图层属性**对话框中的**对齐**选项的值 （**主页**选项卡，在**编辑**组中，单击**图层**，，然后单击**图层属性**）。
  
要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 Snap 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |Layers.Snap [ *i* ] 其中*i* = < 1 >，2，3...  <br/> |
   
若要从某个程序按索引获取对 Snap 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionLayer** <br/> |
|行索引：  <br/> |**visRowLayer** +  *i*其中*i* = 0、 1、 2...  <br/> |
|单元格索引：  <br/> |**visLayerSnap** <br/> |
   

