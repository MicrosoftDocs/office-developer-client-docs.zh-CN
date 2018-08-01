---
title: Print 单元格（“Layers”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm825
localization_priority: Normal
ms.assetid: 9c76bf02-7269-65bb-2fd2-920243d962ef
description: 指定是否可打印属于该图层的形状。
ms.openlocfilehash: cd5b2830ba8bd20cb435cdc2bca4bd55fd5a5438
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780975"
---
# <a name="print-cell-layers-section"></a>Print 单元格（“Layers”部分）

指定是否可打印属于该图层的形状。
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |能够打印形状。  <br/> |
|FALSE  <br/> |不能打印形状。  <br/> |
   
## <a name="remarks"></a>注解

还可以使用 **“图层属性”** 对话框（在 **“开始”** 选项卡上的 **“编辑”** 组中，单击 **“图层”**，然后单击 **“图层属性”**）中的 **“打印”** 选项设置此值。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Print 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |Layers.Print [ *i* ] 其中*i* = < 1 >，2，3...  <br/> |
   
若要从某个程序按索引获取对 Print 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionLayer** <br/> |
|行索引：  <br/> |**visRowLayer** +  *i*其中*i* = 0、 1、 2...  <br/> |
|单元格索引：  <br/> |**visDocPreviewScope** <br/> |
   

