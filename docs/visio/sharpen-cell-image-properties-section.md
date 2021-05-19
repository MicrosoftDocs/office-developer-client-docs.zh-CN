---
title: Sharpen 单元格（“Image Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm910
localization_priority: Normal
ms.assetid: aa2bebfc-a6bb-a6b3-3ae9-8553f96b5738
description: 锐化位图图像。默认值是 0%。通过增加相邻像素的对比度来锐化图像可以使图像更鲜明。
ms.openlocfilehash: e519cf6e5a168b64b4bc8aa083843163a47525ba
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415920"
---
# <a name="sharpen-cell-image-properties-section"></a>Sharpen 单元格（“Image Properties”内容）

锐化位图图像。默认值是 0%。通过增加相邻像素的对比度来锐化图像可以使图像更鲜明。
  
## <a name="remarks"></a>备注

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Sharpen 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Sharpen  <br/> |
   
要从某个程序按索引获取对 Sharpen 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowImage** <br/> |
| 单元格索引：  <br/> |**visImageSharpen** <br/> |
   

