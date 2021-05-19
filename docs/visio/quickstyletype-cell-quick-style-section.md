---
title: 'QuickStyleType Cell (Quick Style Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e7470417-0d70-433e-9496-604ca2eafee6
description: 确定形状继承 (二维、一维或) 快速样式类型。
ms.openlocfilehash: 95aced62c6397fc3229de29b98d3f18e5f69d05b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410502"
---
# <a name="quickstyletype-cell-quick-style-section"></a>QuickStyleType Cell (Quick Style Section) 

确定形状继承 (二维、一维或) 快速样式类型。 
  
|**值**|**说明**|
|:-----|:-----|
|0  <br/> |Visio自动选择  <br/> |
|1  <br/> |一维  <br/> |
|2  <br/> |二维  <br/> |
|3  <br/> |连接器  <br/> |
   
## <a name="remarks"></a>备注

若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **QuickStyleType** 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | QuickStyleType  <br/> |
   
若要从程序按索引获取对 **QuickStyleType** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowQuickStyleProperties** <br/> |
| 单元格索引：  <br/> |**visQuickStyleType** <br/> |
   

