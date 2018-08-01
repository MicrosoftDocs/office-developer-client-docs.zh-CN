---
title: PlaceDepth 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1230
localization_priority: Normal
ms.assetid: 02c139db-fe67-f550-1d07-8c8a9a4fb427
description: 确定在创建布局之前分析绘图使用的方法，并确定布局的类型。
ms.openlocfilehash: ab2c83a94c3dd03c1fdbf0c3ee187076406b2e84
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780854"
---
# <a name="placedepth-cell-page-layout-section"></a>PlaceDepth 单元格（“Page Layout”部分）

确定在创建布局之前分析绘图使用的方法，并确定布局的类型。
  
|**值**|**垂直和水平布局的放置深度**|**自动常量**|
|:-----|:-----|:-----|
| 0  <br/> | 页面默认值  <br/> |**visPLOPlaceDepthDefault** <br/> |
| 1  <br/> | 中等  <br/> |**visPLOPlaceDepthMedium** <br/> |
| 2  <br/> | 深  <br/> |**visPLOPlaceDepthDeep** <br/> |
| 3  <br/> | 浅  <br/> |**visPLOPlaceDepthShallow** <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 PlaceDepth 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | PlaceDepth  <br/> |
   
要从某个程序按索引获取对 PlaceDepth 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPageLayout** <br/> |
| 单元格索引：  <br/> |**visPLOPlaceDepth** <br/> |
   

