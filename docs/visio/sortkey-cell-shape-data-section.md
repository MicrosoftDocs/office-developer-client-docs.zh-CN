---
title: SortKey 单元格（“Shape Data”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251345
localization_priority: Normal
ms.assetid: 67fa5389-f0b9-a9db-8d19-9b16e256dfa3
description: 对影响在“形状数据”窗口中列出的项目的顺序的字符串求值。
ms.openlocfilehash: 1dbc093f2cee509531b8148563fbdb1a777a349f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781420"
---
# <a name="sortkey-cell-shape-data-section"></a>SortKey 单元格（“Shape Data”部分）

对影响在 **“形状数据”** 窗口中列出的项目的顺序的字符串求值。 
  
## <a name="remarks"></a>说明

用于比较 SortKey 值计算是特定于区域设置和区分大小写。 如果 SortKey 值相等，形状数据行顺序列出。 没有排序关键字的形状数据列包含排序关键字的形状数据之后。
  
在下面的示例中，使用排序关键字在 **“形状数据”** 窗口中显示形状数据，显示顺序为：项目编号、数量、价格。 
  
 *Label、、 行*和*SortKey*引用单元格的形状数据行。 在这种情况下，已命名的形状数据行。 
  
|**Row**|**标签**|**SortKey**|
|:-----|:-----|:-----|
| Prop.Item  <br/> | 项目编号  <br/> | 1  <br/> |
| Prop.Price  <br/> | 价格  <br/> | 3  <br/> |
| Prop.Quan  <br/> | 数量  <br/> | 2  <br/> |
   
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 SortKey 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 属性。 *名称*。SortKey 其中属性。 *Name*是自定义属性行的名称  <br/> |
   
若要从某个程序按索引获取对 SortKey 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionProp** <br/> |
| 行索引：  <br/> |**visRowProp** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visCustPropsSortKey** <br/> |
   

