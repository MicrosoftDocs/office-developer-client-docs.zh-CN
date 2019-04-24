---
title: SortKey 单元格（“Hyperlinks”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60086
localization_priority: Normal
ms.assetid: 93d7b00c-bd34-6b4e-44fe-afeb8aa9a294
description: 确定超链接在快捷菜单上显示的顺序的数字。
ms.openlocfilehash: 002ab036f5305aa6daa631c15b0e9eb6148a9635
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335215"
---
# <a name="sortkey-cell-hyperlinks-section"></a>SortKey 单元格（“Hyperlinks”内容）

确定超链接在快捷菜单上显示的顺序的数字。
  
## <a name="remarks"></a>注解

超链接按照从低到高的顺序在快捷菜单上显示，最低的数字显示在菜单的顶部。如果两个超链接行具有相同的 SortKey 单元格值，则顺序由物理行顺序确定。默认值为 0（零）。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 SortKey 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |超链接。 *名称*。在其中的超链接的排序关键字 *。 name*为行名称  <br/> |
   
若要从某个程序按索引获取对 SortKey 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionHyperlink** <br/> |
|行索引：  <br/> |**visRow1stHyperlink** +  *i* = ** 0、1、2 .。。  <br/> |
|单元格索引：  <br/> |**visHLinkSortKey** <br/> |
   

