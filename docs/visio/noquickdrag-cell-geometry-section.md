---
title: NoQuickDrag 单元格（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm80004
localization_priority: Normal
ms.assetid: 8491f459-9de2-8e75-5532-7d3bd0986734
description: 确定形状是否可以选择或拖动当用户单击由 geometry 内容定义的填充的区域。
ms.openlocfilehash: 7d4ffd876d8676af885b8f750fecf6f6d0deaa9b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780801"
---
# <a name="noquickdrag-cell-geometry-section"></a>NoQuickDrag 单元格（“Geometry”部分）

确定形状是否可以选择或拖动当用户单击由 geometry 内容定义的填充的区域。
  
## <a name="remarks"></a>说明

若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 NoQuickDrag 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |Geometry *i* 。NoQuickDrag，其中 * 我 *-< 1 >，2，3...  <br/> |
   
若要从某个程序按索引获取对 NoQuickDrag 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionFirstComponent** +  *i* ，其中*i* = 0、 1、 2...  <br/> |
|行索引：  <br/> |**visRowComponent** <br/> |
|单元格索引：  <br/> |**visCompNoQuickDrag** <br/> |
   

